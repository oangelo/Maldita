# Maldita — Debug de torque em velocidade zero (sessão de HFI)

**Data:** 2026-04-21

## Objetivo
Resolver a falta de torque dos motores em velocidade zero (arrancada em rampa/lombada parada).

## Hardware
- 2x Flipsky BLDC 6374 190KV (saliência alta, mas SPM)
- 1x Spintend Ubox V2 75V 100Ax2 J (dual VESC, CAN-bus)
- 16S6P, ~59.2V nominal
- Controle Spintend Uni1 V2
- Firmware VESC v6.06

## Parâmetros detectados (FOC Detection Wizard)

| Parâmetro | VESC 58 | VESC 116 |
|-----------|---------|----------|
| Motor R | 13.87 mΩ | 17.48 mΩ |
| Motor L | 19.71 µH | 20.42 µH |
| Motor Lq-Ld | 7.45 µH | 8.04 µH |
| Flux Linkage | 4.42 mWb | 4.43 mWb |
| Sensors | Hall | Hall |

**Observações:** Flux linkage consistente entre motores. Saliência de ~38% parecia boa pra HFI na teoria. Diferença de 26% na resistência entre motores merece investigação (cabeamento ou conexões).

## O que tentamos

### 1. Ativação do HFI
- `Sensor Mode`: testado `HFI`, `45 Deg V0V7 HFI (Silent)`, `VSS`
- Nota: descobri que no VESC atual não existe "HFI + Hall Sensors" combinado como eu tinha sugerido inicialmente. HFI funciona puro, com fallback pro observer BEMF acima de `Sensorless ERPM HFI`
- HFI só fica ativo quando há comando de corrente. Em idle puro sem throttle, não injeta

### 2. Ajustes de voltages do HFI (várias iterações)

| Parâmetro | Default | Tentativas | Observação |
|-----------|---------|------------|-----------|
| HFI Start Voltage | 20V | 8V → 15V → 20V | Aumentar não melhorou |
| HFI Run Voltage | 4V | 4V → 8V → 15V | |
| HFI Max Voltage | 6V | 6V → 15V → 25V | |
| HFI Gain | 0.3 | 0.1 → 0.3 → 1.0 | |
| Sensorless ERPM HFI | 3000 | 3000 → 10000 | |
| Ambiguity Resolve Current | 60A | 60A → 40A | Menos tranco na partida |

### 3. Diagnóstico via RT Data → Rotor Position

**Capturas feitas:** Observer com motor sob rotor_lock_openloop 1A, 3A, 5A

**Resultado:** Observer oscila ±20-30° em vez de ficar estável. Em movimento, acompanha mas com erro angular significativo. Conclusão: HFI estima posição com qualidade insuficiente pra gerar torque confiável em zero.

### 4. Comandos de terminal úteis descobertos
- `rotor_lock_openloop <current> <time> <angle>` — trava rotor pra teste
- `foc_openloop <current> <erpm>` — rotação em malha aberta
- `foc_plot_hfi_en 1` — habilita debug plot de HFI
- `faults` / `faults_reset` — gerenciamento de falhas

## Conclusão sobre HFI
**HFI não é viável nesse motor específico.** Saliência medida (7.45 µH) parece boa no papel mas provavelmente é saliência de saturação, não magnética real. Típico de outrunner SPM como o 6374. Aumentar voltages piorou a estimativa (saturação suprime saliência residual).

## Decisão
Voltar pra `Sensor Mode = Hall Sensors` e compensar com otimizações de FOC.

## Problemas identificados além do torque em zero

**Roda presa não faz força enquanto a outra gira:** pode ser configuração de dual VESC via CAN (não HFI). Investigar após aplicar otimizações.

**Diferença de resistência entre motores (13.87 vs 17.48 mΩ):** investigar conexões/cabeamento do motor 116.

## Testes que validaram/invalidaram hipóteses

| Teste | Resultado |
|-------|-----------|
| HFI som em idle | Só chia com comando de corrente ativo (normal) |
| Transição HFI→observer | Funciona: chia parado, silencia acelerando, volta a chiar ao desacelerar |
| Observer com roda manual | Sem comando, observer desliga (teste inválido) |
| Observer com rotor_lock | Oscilações grandes, HFI instável |
| Aumento de voltage | Piorou (saturação, contraintuitivo) |
| Saliência efetiva | Insuficiente pra HFI confiável |

## Solução alternativa se Hall não for bom o suficiente
- Encoder magnético absoluto no eixo (AS5047P, MT6701) via VESC Express
- Redução mecânica maior (70T → 85T ou 90T) pra multiplicar torque nas rodas
- Ambas as soluções evitam a limitação elétrica do HFI em motores SPM

---

**Próxima sessão:** aplicar as otimizações do backlog, testar dual VESC via CAN, validar arrancada em lombada real.
