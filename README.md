# Maldita

Backup de configurações do skate elétrico Maldita.

## Componentes

| Sistema | Componente |
|---|---|
| ESC | Spintend Ubox V2 75V 100A (dual) |
| Motor | Flipsky BLDC 6374 190KV 3250W (x2) |
| Controle Remoto | Spintend Uni1 V2 |
| Bateria | 16S6P, 59.2V nominal, Daly BMS WiFi |
| Rodas | Pneumático 260×85mm (10"×3"), ~50 PSI |
| Transmissão | Corrente 25H, pinhão 9T / coroa 70T (7.78:1) |
| Suspensão | Amortecedor com mola vermelha (a melhorar) |
| Firmware | VESC v6.06 |

## Documentação

- [Controles (ESC + Remoto)](docs/controles.md)
- [Trem de Força (Motor + Transmissão)](docs/trem-de-forca.md)
- [Suspensão](docs/suspensao.md)

## Estrutura

```
Maldita/
├── configs/            # Backups das configurações do VESC Tool
│   ├── motor/
│   ├── app/
│   └── imu/
├── hardware/
│   ├── schematics/
│   ├── pcb/
│   └── mechanical/
│       └── fotos/      # Fotos dos componentes
└── docs/               # Documentação detalhada por subsistema
```

## Licença

A definir.
