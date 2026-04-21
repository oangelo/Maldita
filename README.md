# Maldita

Backup de configurações do skate elétrico Maldita.

## Hardware

- **ESC**: UBOX_V2_75 (Spintend Ubox V2 75V 100A x2 J) — a plaquinha vermelha da Maldita
- **Topologia**: Dual ESC (dois canais independentes)
- **Tensão**: 16–75V (pico < 80V)
- **Corrente máxima**: 100A por canal / 200A total
- **Dimensões**: 130 × 83 × 27mm / 396g
- **Saída 12V**: máx 3A (luz + buzina)
- **Saída 5V**: máx 500mA

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

- **Marca**: Spintend
- **Modelo**: Uni1 V2
- **Tela**: OLED (dados em tempo real)
- **Bateria**: Lithium 450mAh (~11h de duração)
- **Frequência**: 2.4GHz
- **Protocolo**: PPM ou UART (configurável)
- **CanBus**: On/Off pelo controle
- **Botão extra**: Controle de luz de freio / farol / buzina
- **Firmware**: Bootloader, suporte a atualização online
- **Compatibilidade**: VESC, Spintend Ubox V2

## Bateria

- **Configuração**: 16S6P
- **Tensão nominal**: 59.2V (16 × 3.7V)
- **Tensão carga cheia**: 67.2V (16 × 4.2V)
- **BMS**: Daly Smart BMS com módulo WiFi
- **Células**: Antigas (< 2500mAh por célula)
- **Capacidade estimada**: < 15Ah (6 × < 2500mAh)

## Rodas

- **Pneu**: 260 × 85 (3.00-4 / 10"x3") pneumático
- **Diâmetro externo**: 260mm
- **Largura**: 85mm
- **Tipo**: Pneumático com câmara de ar
- **Pressão**: ~50 PSI

## Transmissão

- **Tipo**: Corrente (chain drive)
- **Pinhão do motor**: 04C, 9T, furo 8mm, aço 45#
- **Coroa da roda**: 25H, 70T, 29mm (original: 47T — trocada por mais torque)
- **Relação de marcha**: 7.78:1

## Velocidade Máxima Teórica

| Condição | Velocidade |
|---|---|
| Nominal (59.2V) | 70.9 km/h |
| Carga cheia (67.2V) | 80.4 km/h |
| Estimada na prática (~80%) | 57–64 km/h |

> Cálculo: 190KV × 59.2V = 11.248 RPM → / 7.78 = 1.446 RPM roda → × π × 0.260m = 70.9 km/h

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
