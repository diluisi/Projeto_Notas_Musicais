# Notas musicais

## Objetivos

Ajudar as pessoas a estudar teoria musical

* Escalas musicais

* Formações de acordes

* Campos harmônicos

* Progressões harmônicas

## Como?

Eu gostaria de fazer uma aplicação de terminal (CLI) que ao ser perguntada uma escala ou um campo harmônico, ele exia uma tabela com uma progressão sugerida randomicamente.

## Notas

Notas: Dó-Ré-Mi-Fá-Sol-Lá-Si

Notas e acidentes: Dó-Dó#-Ré-Ré#-Mi-Fá-Fá#-Sol-Sol#-Lá-Lá#-Si

## Cifras

C-C#-D-D#-E-F-F#-G-G#-A-A#-B

| Nome da nota | Naturais | Sustenidos (#) | Bemóis(b) |
| ------------ | -------- | -------------- | --------- |
| Dó           | C        | C#             | C`b`      |
| Ré           | D        | D#             | Db        |
| Mi           | E        | E#             | Eb        |
| Fá           | F        | F#             | Fb        |
| Sol          | G        | G#             | Gb        |
| Lá           | A        | A#             | Ab        |
| Si           | B        | B#             | Bb        |

## Escalas

Graus: I (tônica) - II - III - IV - V - VI - VII

## Escala maior

Intervalos: T - T - ST - T - T - T - ST

| I   | II  | III | IV  | V   | VI  | VII |
| --- | --- | --- | --- | --- | --- | --- |
| T   | T   | ST  | T   | T   | T   | ST  |
| C   | D   | E   | F   | G   | A   | B   |
| C#  | D#  | F   | F#  | G#  | A#  | C   |

## Escala menor

Intervalos: T - ST - T - T - ST - T - T

| I   | II  | III  | IV  | V   | VI  | VII |
| --- | --- | ---- | --- | --- | --- | --- |
| T   | ST  | T    | T   | ST  | T   | T   |
| C   | D   | D`#` | F   | G   | G#  | A#  |

## Acordes

**Tríade (Maior)**: Formado pelo Grau I (Tônica) + Grau III (Terça) + Grau V

**Sétima**: Acrescentamos o Grau VII no acorde

**Tríade Menor**: Grau I + Grau III *b* (semi tom para trás) + Grau V

**Tríade Diminuta**: Grau I + Grau III *b* (semi tom para trás) + Grau V *b* (semi tom para trás)

## Campo Harmônico

| I       | ii      | iii     | IV      | V       | vi      | VII°       |
| ------- | ------- | ------- | ------- | ------- | ------- | ---------- |
| T       | T       | ST      | T       | T       | T       | ST         |
| C maior | D menor | E menor | F maior | G maior | A menor | B diminuto |

## Progressões Harmônicas

I - IV - V (mais comum- músicas chicletes)

-------

-----

# Exemplos de Uso

```bash
notas-musicais c maior
```

Retorno:

| I   | II  | III | IV  | V   | VI  | VII |
| --- | --- | --- | --- | --- | --- | --- |
| C   | D   | E   | F   | G   | A   | B   |

```bash
notas-musicais c maior --acordes | --campo | --harmonico | --chords
```

| I       | ii      | iii     | IV      | V       | vi      | VII°       |
| ------- | ------- | ------- | ------- | ------- | ------- | ---------- |
| C maior | D menor | E menor | F maior | G maior | A menor | B diminuto |


