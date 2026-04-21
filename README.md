# Maldita

Backup de configurações do skate elétrico Maldita.

## Hardware

- **ESC**: UBOX_V2_75 (Ubox V2 75V 100A x2 J) — a plaquinha vermelha da Maldita
- **Topologia**: Dual ESC (dois canais independentes)
- **Tensão máxima**: 75V
- **Corrente máxima**: 100A por canal

## Motores

- **Modelo**: Flipsky BLDC 6374 190KV 3250W (x2)
- **Tipo**: Motor de correia para skate elétrico
- **KV**: 190KV
- **Potência**: 3250W cada
- **Proteção**: À prova d'água e à prova de poeira

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
