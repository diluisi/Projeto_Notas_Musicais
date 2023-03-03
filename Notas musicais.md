# Aula 1: Especificação - Projeto Notas musicais

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

# Aula 2: Criando nosso amiente de pacote Python com Poetry, linters, testes e documentação

O primeiro passo é instalar o Poetry, pois assim poderemos:

* fazer o build;

* separar as dependências de desenvolvimento, documentação, subir para o PyPi;

* gerenciador de ambientes, instalação

Assistir a live do Poetry ([Gerenciando pacotes e ambientes com Poetry - Live de Python #179 - YouTube](https://www.youtube.com/watch?v=ZOSWdktsKf0))


## Poetry

Criando um projeto em Poetry:

```bash
poetry new notas-musicais
```

Se entrarmos no projeto e dermos um comando 'lt' veremos a estrutura de árvore.

Veremos a estrutura do projeto já criada como os arquivos init, tests, pasta do projeto.

![](/home/diluisi/snap/marktext/9/.config/marktext/images/2023-03-03-12-01-28-image.png)

Você pode perceer que colocamos o hífen no nome da pasta, porém, em Python, não é recomendável utilizar hífen como a pasta do projeto. Por esta razão vemos um underscore.

## Git

Vamos iniciar nosso projeto com Git para fazermos os controles de versões:

```bash
git init .
```

Agora o próximo passo é subir o projeto para o GitHub:

```bash
gh repo create
```

Um detalhe impotante é se certifica que suas credenciais estejam associadas a sua conta pessoal ou uma conta de empresa.

O próximo passo é escolher se queremos criar um repositório novo do zero ou se queremos utilizar um repositório local para fazer upload no GitHub. Escolhemos a segunda opção.

![](/home/diluisi/snap/marktext/9/.config/marktext/images/2023-03-03-12-00-47-image.png)

Dica de estudo: https://cli.github.com

No link dá para ver issues, criar tags e outras coisas que não conseguimos somente via CLI do git, pois são coisas específicas do GitHub.

Projeto criado:

![](/home/diluisi/snap/marktext/9/.config/marktext/images/2023-03-03-12-05-17-image.png)

No entanto, precisamos criar o git ignore que ajuda o GitHub a não subir alguns arquivos que não queremos.

Instalamos o ignr via pip install ignr para criarmos automaticamente os arquivos que queremos ignorar.

``` bash
ignr -p python > .gitignore
```

Ok! Agora temos o suficiente para subir para o GitHub. Observe que colocamos o ponto final que significa "subir tudo", mas use com moderação, pois nem sempre é recomendável fazer isso.

```bash
git add .
git commit -m "Commit inicial- Estrutura do Projeto"
git push --set-upstream origin main
```

O terceiro comando é para o primeito git push do projeto. Posteriormente, não precisaremos fazer isso novamente, apenas git push.

## pytest

Assistir a live do pytest: [Pytest: Uma introdução - Live de Python #167 - YouTube](https://www.youtube.com/watch?v=MjQCvJmc31A&t=0s)

Documentação: [Welcome to pytest-cov’s documentation! &#8212; pytest-cov 4.0.0 documentation](https://pytest-cov.readthedocs.io/en/latest/)

A live 168 também é interessante sobre fixtures.

Antes de adicionar o pytest, nós temos que criar um **grupo de desenvolvimento** para este projeto. Isto significa que iremos isolar esta dependência no pyproject que é especificamente de desenvolvimento.

![](/home/diluisi/snap/marktext/9/.config/marktext/images/2023-03-03-12-41-31-image.png)

Este é o nosso projeto no Poetry. A única dependência de desenvolvimento é o python 3.10. 

```bash
poetry add --group dev pytest
```

![](/home/diluisi/snap/marktext/9/.config/marktext/images/2023-03-03-12-44-54-image.png)

Agora se olharmos as dependências do projeto é possível notar o novo grupo criado:

![](/home/diluisi/snap/marktext/9/.config/marktext/images/2023-03-03-12-45-58-image.png)

Cada programador tem seu estilo de criar código e realizar testes. O ideal é que façamos um teste de cobertura para sabermos se estamos cobrindo os principais trechos do código. Para isso existe uma ferramenta muito útil chamada pytest-cov que vem de *coverage*. Ele roda todos os teste e gera coberturas de quais trechos não estão sendo verificados.

```bash
poetry add --group dev pytest-cov
```

![](/home/diluisi/snap/marktext/9/.config/marktext/images/2023-03-03-12-52-37-image.png)

## Padronização do estilo de código - PEP 8

Fonte: [PEP 8 – Style Guide for Python Code | peps.python.org](https://peps.python.org/pep-0008/)

Fonte 2: https://pep8.org/

Um exemplo de padrão é o *Vertical Hanging Indent*.

Em nosso projeto utilizaremos o Blue

[Blue &#8212; Blue 0.9.1 documentation](https://blue.readthedocs.io/en/latest/)

Uma outra formatação importante é ter os "imports" ordenados. Utilizaremos o isort

```bash
poetry add --group dev blue
poetry add --group dev isort
```




