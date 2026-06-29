# projeto-ETL-python
Projeto de ETL com python utilizando as bibliotecas pandas, statistics e seaborn.

# ETL de Dados de Funcionários com Python

Projeto de ETL (Extract, Transform, Load) desenvolvido em Python com o objetivo de realizar a limpeza, padronização e tratamento de um conjunto de dados fictício de funcionários.

O projeto foi desenvolvido utilizando apenas as bibliotecas **Pandas**, **Statistics** e **Seaborn**.

---

## Objetivo

O objetivo deste projeto é demonstrar as principais etapas de um processo de ETL utilizando Python, preparando um conjunto de dados para futuras análises.

As transformações realizadas incluem:

- Limpeza de dados
- Padronização de informações
- Conversão de tipos de dados
- Tratamento de valores ausentes
- Remoção de inconsistências
- Exportação do dataset tratado

---

## Tecnologias utilizadas

- Python 3
- Pandas
- Statistics
- Seaborn

---

## Estrutura do Projeto

```
ETL-Funcionarios/
│
├── dataset_funcionarios.csv              # Dataset original
├── dataset_funcionarios_ETL_final.csv      # Dataset após o ETL
├── Análise dos dados.py                   # Código principal
├── README.md
```

---

## Processo de ETL

### Extração (Extract)

Foi realizada a leitura do arquivo CSV utilizando a biblioteca Pandas.

```python
import pandas as pd

dataset = pd.read_csv("dataset_funcionarios.csv")
```

---

### Transformação (Transform)

O tratamento foi realizado separadamente para cada coluna.

### Nome

- Remoção de espaços extras;
- Padronização para letras maiúsculas apenas no início das palavras;
- Verificação de valores nulos e duplicados.

Exemplo:

Antes

```
JOÃO   SILVA
```

Depois

```
João Silva
```

---

### Idade

Foram realizadas as seguintes etapas:

- Conversão para tipo numérico;
- Identificação de valores inválidos;
- Tratamento de valores ausentes;
- Substituição dos valores nulos pela média da coluna.

---

### Salário

Foi realizado:

- Remoção do símbolo "R$";
- Remoção dos separadores de milhares;
- Conversão para tipo numérico;
- Remoção de salários negativos;
- Preenchimento dos valores ausentes utilizando a média.

---

### Estado

Foi realizada a padronização dos estados brasileiros.

Exemplo:

| Antes | Depois |
|-------|--------|
| SP | São Paulo |
| RJ | Rio de Janeiro |
| MG | Minas Gerais |

Essa padronização evita que o mesmo estado seja tratado como categorias diferentes.

---

### Data de Admissão

As datas estavam armazenadas em diferentes formatos.

Foi utilizada a função `pd.to_datetime()` para converter todos os registros para o formato de data do Pandas e, posteriormente, padronizados para o formato brasileiro.

Exemplo:

Antes

```
2020-05-17
17/05/2020
05-17-2020
```

Depois

```
17/05/2020
```

---

### Cargo

Foi realizada:

- Remoção de espaços extras;
- Padronização das letras utilizando o formato Title Case.

Exemplo:

Antes

```
analista
ANALISTA
Analista
```

Depois

```
Analista
```

---

## Validação

Ao final do processo foram realizadas verificações para garantir a qualidade dos dados utilizando:

- `info()`
- `describe()`
- `isnull().sum()`

---

## Carga (Load)

Após todas as transformações, o conjunto de dados tratado foi exportado para um novo arquivo CSV.

```python
dataset.to_csv("dataset_funcionarios_tratado.csv", index=False)
```

---

## Resultados

Após o ETL o conjunto de dados passou a apresentar:

- Dados padronizados;
- Tipos de dados corretos;
- Ausência de inconsistências;
- Valores ausentes tratados;
- Informações prontas para análises estatísticas e visualizações.

---

## Aprendizados

Durante o desenvolvimento deste projeto foram praticados conceitos como:

- ETL
- Limpeza de dados
- Manipulação de DataFrames
- Tratamento de valores ausentes
- Conversão de tipos
- Padronização de informações
- Organização de código em etapas
- Boas práticas em projetos de Ciência de Dados

---

## Autor

**Kewyn Montani Zancope**

Projeto desenvolvido para como prática de ETL utilizando Python.
