# Maldita

Backup de configurações do skate elétrico Maldita.

## Hardware

- **ESC**: UBOX_V2_75 (Ubox V2 75V 100A x2 J) — a plaquinha vermelha da Maldita
- **Topologia**: Dual ESC (dois canais independentes)
- **Tensão máxima**: 75V
- **Corrente máxima**: 100A por canal

## Motores

- **Modelo**: Flipsky BLDC 6374 190KV 3250W (x2)
- **Tipo**: Brushless DC (BLDC), sensorless / Hall
- **KV**: 190KV
- **Potência**: 3250W cada
- **Corrente máx**: 85A
- **Tensão máx**: 12S (50.4V)
- **Torque máx**: 8Nm
- **Resistência**: 0.05 Ohm
- **Polos**: 14 (7 pares)
- **Ímãs**: N42SH
- **Eixo**: 8mm x 32mm, chaveta 3x3x20mm
- **Peso**: 0.86kg cada
- **Dimensões**: 63mm x 74mm
- **Proteção**: À prova d'água e à prova de poeira

## Controle Remoto

- **Modelo**: Tela remota com receptor único (Uni1 versão 2)
- **Compatibilidade**: VESC, Spintend Ubox V2
- **Frequência**: 2.4GHz

## Transmissão

- **Tipo**: Corrente (chain drive)
- **Pinhão do motor**: 04C, 9T, furo 8mm, aço 45#
- **Coroa da roda**: 25H, 70T, 29mm (original: 47T — trocada por mais torque)
- **Relação de marcha**: 7.78:1

## Firmware

- **Versão**: v6.06 (base VESC)

## Estrutura

```
Maldita/
├── configs/            # Backups das configurações do VESC Tool
│   ├── motor/          # Configs do motor (FOC, detection, etc.)
│   ├── app/            # Configs do app (PPM, UART, ADC, etc.)
│   └── imu/            # Configs do IMU
├── hardware/           # Esquemas e docs da UBOX_V2_75
│   ├── schematics/
│   ├── pcb/
│   └── mechanical/
└── docs/               # Notas, procedimentos, guias
```

## Como Exportar Configs (VESC Tool v6.06)

1. Conecte o ESC via USB
2. Vá em **File → Export full configuration**
3. Salve o arquivo XML na pasta `configs/` correspondente
4. Para motor duplo: exporte configs do motor 1 e motor 2 separadamente

## Como Restaurar Configs

1. Conecte o ESC via USB
2. Vá em **File → Import full configuration**
3. Selecione o arquivo XML do backup
4. Apply e escreva na flash

## Licença

A definir.
