# UBOX_V2_75 — Hardware Specs

## Identificação

- **Nome**: UBOX_V2_75
- **Fabricante**: Spintend
- **Descricao**: Ubox V2 75V 100A x2 J (dual ESC)
- **Placa**: PCB vermelha ("a plaquinha vermelha da Maldita")

## Especificacoes Eletricas

| Parametro | Valor |
|---|---|
| Tensao | 16-75V (pico < 80V) |
| Corrente maxima (por canal) | 100A |
| Corrente dual maxima | 200A total |
| Canais | 2 (dual) |
| Saida 12V | Max 3A (luz + buzina dividem) |
| Saida 5V | Max 500mA |
| Dimensoes | 130 x 83 x 27mm (com parafusos) |
| Peso | 396g |
| Cabo motor | 12AWG 12cm |
| Cabo bateria | 10AWG 12cm |

## Conectores

- (a documentar)

## Componentes Principais

- MCU: (a documentar)
- MOSFETs: (a documentar)
- Driver: (a documentar)

## Controle Remoto

| Parametro | Valor |
|---|---|
| Fabricante | Spintend |
| Modelo | Uni1 V2 |
| Tela | OLED (dados em tempo real) |
| Bateria | Lithium 450mAh |
| Duracao | ~11 horas |
| Frequencia | 2.4GHz |
| Protocolo | PPM ou UART (configuravel) |
| CanBus | On/Off pelo controle |
| Botao extra | Controle de luz de freio / farol / buzina |
| Porta IO | Para buzina e luz |
| Firmware | Bootloader, suporte a atualizacao online |
| Compatibilidade | VESC, Spintend Ubox V2 |
| Receptor | Integrado na UBox V2 (ou receptor unico separado) |

## Motores

### Specs Gerais

| Parametro | Valor |
|---|---|
| Modelo | Flipsky BLDC 6374 190KV 3250W |
| Quantidade | 2 (dual, um por canal) |
| Tipo | Brushless DC (BLDC) |
| KV | 190KV |
| Potencia maxima | 3250W cada |
| Corrente maxima | 85A |
| Tensao maxima | 12S (50.4V) |
| Torque maximo | 8Nm |
| Resistencia | 0.05 Ohm |
| Protecao | A prova d'agua e a prova de poeira |

### Eletrico / Magnetico

| Parametro | Valor |
|---|---|
| Numero de polos | 14 (7 pares de polos) |
| Ima | N42SH (alta temperatura) |
| Estator | Aco japones laminado, 0.2mm de espessura |
| Sensores | Hall Effect 120 graus, fio sensor JST-ZH 6pin 1.5mm pitch |
| Modo | Sensorless (comum) ou com sensores Hall |

### Dimensoes e Mecanico

| Parametro | Valor |
|---|---|
| Diametro | 63mm |
| Comprimento | 74mm |
| Eixo | 8mm diametro, 32mm comprimento |
| Chaveta | 3x3x20mm (chave incluida) |
| Peso | 0.86kg / 1.9 lb |
| Parafusos montagem | M4 (nao incluidos) |

### Fiacao

| Cor | Fase |
|---|---|
| Azul | A |
| Preto | B |
| Amarelo | C |

- Fios: silicone 12AWG, 130mm, conector bullet 4.0mm (macho)

## Bateria

| Parametro | Valor |
|---|---|
| Configuracao | 16S6P |
| Tensao nominal | 59.2V (16 x 3.7V) |
| Tensao carga cheia | 67.2V (16 x 4.2V) |
| BMS | Daly Smart BMS com modulo WiFi |
| Celulas | Antigas (< 2500mAh por celula) |
| Capacidade estimada | < 15Ah (6 x < 2500mAh) |

## Rodas

| Parametro | Valor |
|---|---|
| Designacao | 3.00-4 / 10"x3" / 260x85 |
| Diametro externo | 260mm |
| Largura | 85mm |
| Tipo | Pneumatico com camara de ar |
| Pressao | ~50 PSI |
| Aro | 4" (~102mm) |

## Transmissao

| Parametro | Valor |
|---|---|
| Tipo | Corrente (chain drive) |
| Pinhao do motor | 04C, 9T, furo 8mm |
| Material pinhao | Aco 45#, tratamento superficial de tempra por alta frequencia |
| Passo pinhao | 6.35mm |
| Espessura dente pinhao | 3mm |
| Coroa da roda | 25H, 70T, 29mm |
| Relacao de marcha | 7.78:1 (70/9) |
| Relacao original | 5.22:1 (47/9) — coroa trocada por mais torque |

## Velocidade Maxima Teorica

```
Bateria 16S:
  Nominal:      59.2V
  Carga cheia:  67.2V

Motor 190KV:
  RPM nominal:     190 x 59.2 = 11.248 RPM
  RPM carga cheia: 190 x 67.2 = 12.768 RPM

Relacao de marcha: 7.78:1 (70T / 9T)
  RPM roda nominal:     11.248 / 7.78 = 1.446 RPM
  RPM roda carga cheia: 12.768 / 7.78 = 1.641 RPM

Roda 260mm:
  Circunferencia: pi x 0.260m = 0.817m
```

| Condicao | Velocidade |
|---|---|
| Nominal (59.2V) | 70.9 km/h |
| Carga cheia (67.2V) | 80.4 km/h |
| Estimada na pratica (~80%) | 57-64 km/h |

## Notas

- Placa de cor vermelha, projeto da Spintend/Maldita.
- Compativel com firmware VESC v6.06.
- Cada canal (motor 1 e motor 2) deve ser configurado individualmente no VESC Tool.
- Receptor do controle Uni1 V2 integrado na UBox V2 quando comprado junto.
