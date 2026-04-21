# Configurações VESC

Backups exportados do VESC Tool v6.06.

## Pastas

| Pasta | Conteúdo |
|---|---|
| `motor/` | Configuração FOC, detection do motor, parâmetros elétricos |
| `app/` | Configuração do app: PPM, UART, ADC, nRF, etc. |
| `imu/` | Configuração do IMU (se aplicável) |

## Nomenclatura dos Arquivos

- `motor1_<data>.xml` — Config do motor 1
- `motor2_<data>.xml` — Config do motor 2
- `app_<data>.xml` — Config do app
- `full_<data>.xml` — Exportação completa

Formato de data: `YYYY-MM-DD`

## Exportar pelo VESC Tool

1. Conecte via USB
2. **File → Export full configuration** (exporta tudo)
3. Ou exporte seções individuais nas abas de configuração
