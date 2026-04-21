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

| Parâmetro | Valor |
|---|---|
| Modelo | Flipsky BLDC 6374 190KV 3250W |
| Quantidade | 2 (dual, um por canal) |
| Tipo | Corrente (chain drive) |
| KV | 190KV |
| Potência | 3250W cada |
| Proteção | À prova d'água e à prova de poeira |

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
