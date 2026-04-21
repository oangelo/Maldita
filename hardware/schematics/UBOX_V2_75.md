# UBOX_V2_75 — Hardware Specs

## Identificação

- **Nome**: UBOX_V2_75
- **Descrição**: Ubox V2 75V 100A x2 J (dual ESC)
- **Placa**: PCB vermelha ("a plaquinha vermelha da Maldita")

## Especificações Elétricas

| Parâmetro | Valor |
|---|---|
| Tensão máxima | 75V |
| Corrente máxima (por canal) | 100A |
| Canais | 2 (dual) |
| Topologia | ?

## Conectores

- (a documentar)

## Componentes Principais

- MCU: (a documentar)
- MOSFETs: (a documentar)
- Driver: (a documentar)

## Controle Remoto

| Parâmetro | Valor |
|---|---|
| Modelo | Tela remota com receptor único |
| Versão | Uni1 v2 |
| Frequência | 2.4GHz |
| Compatibilidade | VESC, Spintend Ubox V2 |

## Motores

### Specs Gerais

| Parâmetro | Valor |
|---|---|
| Modelo | Flipsky BLDC 6374 190KV 3250W |
| Quantidade | 2 (dual, um por canal) |
| Tipo | Brushless DC (BLDC) |
| KV | 190KV |
| Potência máxima | 3250W cada |
| Corrente máxima | 85A |
| Tensão máxima | 12S (50.4V) |
| Torque máximo | 8Nm |
| Resistência | 0.05 Ohm |
| Proteção | À prova d'água e à prova de poeira |

### Elétrico / Magnético

| Parâmetro | Valor |
|---|---|
| Número de polos | 14 (7 pares de polos) |
| Ímãs | N42SH (alta temperatura) |
| Estator | Aço japonês laminado, 0.2mm de espessura |
| Sensores | Hall Effect 120°, fio sensor JST-ZH 6pin 1.5mm pitch |
| Modo | Sensorless (comum) ou com sensores Hall |

### Dimensões e Mecânico

| Parâmetro | Valor |
|---|---|
| Diâmetro | 63mm |
| Comprimento | 74mm |
| Eixo | 8mm diâmetro, 32mm comprimento |
| Chaveta | 3x3x20mm (chave incluída) |
| Peso | 0.86kg / 1.9 lb |
| Parafusos montagem | M4 (não incluídos) |

### Fiação

| Cor | Fase |
|---|---|
| Azul | A |
| Preto | B |
| Amarelo | C |

- Fios: silicone 12AWG, 130mm, conector bullet 4.0mm (macho)

## Transmissão

| Parâmetro | Valor |
|---|---|
| Tipo | Corrente (chain drive) |
| Pinhão do motor | 04C, 9T, furo 8mm |
| Material pinhão | Aço 45#, tratamento superficial de têmpera por alta frequência |
| Passo pinhão | 6.35mm |
| Espessura dente pinhão | 3mm |
| Coroa da roda | 25H, 70T, 29mm |
| Relação de marcha | 7.78:1 (70/9) |
| Relação original | 5.22:1 (47/9) — coroa trocada por mais torque |

## Notas

- Placa de cor vermelha, projeto proprietário da Maldita.
- Compatível com firmware VESC v6.06.
- Cada canal (motor 1 e motor 2) deve ser configurado individualmente no VESC Tool.
