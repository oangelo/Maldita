# Maldita — Backlog de Otimizações

Estado atual: `Sensor Mode = Hall Sensors`, HFI descartado (ver sessão 2026-04-21).

---

## Pra qualidade de FOC
- [ ] `Sensor Mode` → `Hall Sensors`
- [ ] Refazer detecção específica dos Halls (`hall_analyze` ou wizard)
- [ ] `FOC → Advanced → Current Sample Mode` → `V0 and V7 Interpolation` (ou `V0 only` se Ubox não suportar phase shunts)
- [ ] `FOC → Advanced → MTPA Mode` → `IQ Target` (aproveita saliência pra torque/A)
- [ ] `FOC → Advanced → Current Decoupling Mode` → `BEMF`
- [ ] `FOC → Hall Sensors → FOC Hall Extra Samples` → 3 ou 4

## Pra dual VESC via CAN
- [ ] VESC mestre: `Controller ID = 0`
- [ ] VESC escravo: `Controller ID = 1`
- [ ] `Send CAN Status` → `Enabled (1, 2, 3, 4, 5)` em ambos
- [ ] Mestre: `Multiple ESCs over CAN` → `Enabled`
- [ ] Escravo: `App to Use` → `None` ou `No App`

## Pra segurança e comportamento
- [ ] `Wattage Max` → valor realista (ex: 3000W)
- [ ] `Soft RPM Limit Start/End` → 70000/80000 ERPM (consistente com velocidade alvo)
- [ ] Configurar sensor de temperatura de motor (se houver NTC interno)

## Pra App Config (throttle)
- [ ] `Control Type` → `Current No Reverse Brake Button`
- [ ] `Positive Ramping Time` → 0.4s
- [ ] `Negative Ramping Time` → 0.2s
- [ ] `Current Boost at Start` → ativar (pico extra na arrancada)
- [ ] `Input Deadband` → 15%

## Problemas abertos
- [ ] Roda presa não faz força enquanto a outra gira (investigar dual VESC via CAN)
- [ ] Diferença de resistência entre motores (13.87 vs 17.48 mΩ) — investigar cabeamento motor 116

## Soluções alternativas (se Hall não for suficiente)
- [ ] Encoder magnético absoluto no eixo (AS5047P, MT6701) via VESC Express
- [ ] Redução mecânica maior (70T → 85T ou 90T) pra multiplicar torque nas rodas
