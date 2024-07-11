# Pós-Graduação em Ciência de Dados e Analytics - PUC RIO (MVP Engenharia de Dados)

## Resumo

Este projeto foi criado para aplicar os conhecimentos adquiridos no módulo de Engenharia de Dados do curso de Especialização em Ciência de Dados e Analytics da PUC-Rio. O objetivo é desenvolver um MVP (produto mínimo viável) de um pipeline de dados, abrangendo as etapas de busca, coleta, modelagem, carga e análise de dados, utilizando as tecnologias da plataforma Databricks.

Os dados para este projeto foram obtidos a partir da pesquisa "Steam Games Dataset 2024", que contém informações relevantes sobre aproximadamente 83.000 títulos na plataforma Steam. O estudo inicial foi realizado por Artemiy Ermilov, Arina Nevolina, Assol Kubaeva e Артем Поспелов, e foi publicado na plataforma Kaggle, estando disponível para consulta pública em [Kaggle](https://www.kaggle.com/datasets/artermiloff/steam-games-dataset).

## Objetivo

O objetivo desse projeto é realizar um processo de ponta a ponta que vá desde a coleta até a análise das informações dos jogos contidos na plataforma Steam. A análise feita terá como objetivo responder as seguintes perguntas:

1) Qual o preço médio por ano dos jogos na Steam?

2) Quais são os 5 jogos com mais DLC (Downloadable Content)?

3) Qual é o jogo com o maior pico de jogadores na Steam?

4) Qual ano teve a maior quantidade de lançamentos de jogos na Steam?

5) Qual jogo tem o maior número de conquistas?

## Catálogo de Dados

| NOME DA COLUNA  | TIPO DE DADO | DESCRIÇÃO | VALORES ACEITÁVEIS |
| ------------- | ------------- | ------------- | ------------- |
| STEAM_ID  | INT | IDENTIFICADOR ÚNICO DO TÍTULO DENTRO DA PLATAFORMA STEAM | VALOR INTEIRO COMEÇANDO NO 0 E INDO ATÉ O TAMANHO DO CATÁLOGO DE PRODUTOS DA PLATAFORMA STEAM, SEM QUE HAJA 2 OU MAIS TÍTULOS REFERENCIANDO O MESMO IDENTIFICADOR. |
| TITLE_NAME | STRING | NOME DO TÍTULO | VALOR TEXTO QUE NÃO SEJA VAZIO. |
| RELEASE_DATE | DATETIME | DATA DE LANÇAMENTO DO TÍTULO | VALOR DO TIPO DATA QUE NÃO TENHA DATAS NO FUTURO. |
| PRICE | DOUBLE | PREÇO PARA A AQUISIÇÃO DO TÍTULO | VALOR NÚMERICO EM DÓLARES (USD) QUE NÃO PODE SER NEGATIVO. |
| DLC_COUNT | INT | NÚMERO DE DLCS DO TÍTULO | VALOR INTEIRO QUE NÃO PODE SER NEGATIVO. |
| ACHIEVEMENT | INT | NÚMERO DE CONQUISTAS QUE PODEM SER OBTIDAS NO TÍTULO | VALOR INTEIRO QUE NÃO PODE SER NEGATIVO. |
| PEAK_CONCURRENT_USERS | INT | NÚMERO MÁXIMO DE JOGADORES CONCORRENTES | VALOR INTEIRO QUE NÃO PODE SER NEGATIVO. |

## Desenvolvimento

O projeto foi desenvolvido utilizando o software chamada [Databricks](https://www.databricks.com/br). Nela, nós fizemos o uso do [DBFS](https://docs.databricks.com/user-guide/dbfs-databricks-file-system.html) para armazenar os dados extraídos e persisti-los no formato Parquet para que a gente pudesse aplicar o conceito da [Medallion Architecture](https://www.databricks.com/glossary/medallion-architecture).

## Conclusão

Ao final desse projeto, foi feita uma análise sobre os dados da base da Steam extraída pelo [Kaggle](https://www.kaggle.com/datasets/artermiloff/steam-games-dataset). Nele, utilizamos frameworks e conceitos referentes ao processamento paralelizado, tendo em vista a necessidade da criação de um pipeline de dados construído de ponta a ponta (Extração, Transformação e Carga). Para finalizar, fizemos as análises necessárias usando o SparkSQL e conseguimos responder todas as perguntas.