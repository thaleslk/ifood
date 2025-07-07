# Case Técnico de Data Analysis - iFood

## 1. Descrição

Projeto Python/Pyspark que consiste em extrair um conjunto de dados sobre pedidos/usuários/restaurantes/teste A/B, 
armazenar em formato de tabelas (ETL), modelar métricas e analisar impactos significativos.

## 2. Ambiente

Esse projeto foi desenvolvido em ambiente **Databricks Free Edition**.

Para preparar o ambiente, são necessários os seguintes passos:
- Criação dos schemas **`bronze`**, **`silver`** e **`gold`** no Default Catalog **`workspace`** (via plataforma)
- Criação do volume **`files`** no schema **`bronze`** (via plataforma)
- Importação dos notebooks no Home Folder (via plataforma ou Git Folder):
  - **`Bronze.ipynb`**
  - **`Silver.ipynb`**
  - **`Silver Analysis.ipynb`**
  - **`Gold.ipynb`**
  - **`Gold Analysis - Part 1.ipynb`**
  - **`Gold Analysis - Part 2.ipynb`**

## 3. Execução

Para executar os notebooks, é necessário anexar o cluster disponível (**serverless**) no notebook e clicar em **Run All**.

Além disso, é essencial executar os notebooks na seguinte ordem:
  1. **`Bronze.ipynb`**
  2. **`Silver.ipynb`**
  3. **`Gold.ipynb`** 

Já os notebooks de análises, a ordem é opcional:
  - **`Silver Analysis.ipynb`** 
  - **`Gold Analysis - Part 1.ipynb`**
  - **`Gold Analysis - Part 2.ipynb`**

## 4. Camadas de armazenamento (ETL)

O armazenamento dos dados desse projeto simula a estrutura de um Datalake, ou seja, dividindo em camadas "Bronze", "Silver" e "Gold".

- **Bronze**: Aqui os dados armazenados são brutos, ou seja, ainda não receberam nenhum tratamento para serem consumidos. 
Nesse projeto, são representados por arquivos ".json.gz", ".csv.gz" e ".tar.gz", onde cada arquivo possui as informações 
coletadas referentes a pedidos, usuários, restaurantes e teste A/B.
- **Silver**: Os dados presentes nessa camada já foram tratados e podem ser consumidos. Nesse projeto, são representados 
por tabelas, onde cada tabela possui determinadas informações dos pedidos, usuários, restaurantes e teste A/B coletados. 
As informações dos itens dos pedidos foram divididas com base nos seus tipos, ou seja, "item geral" e "item de guarnição", 
mas ambas informações na mesma tabela.
- **Gold**: Aqui os dados estão enriquecidos e podem ser utilizados para construção de KPIs e análises de impacto significativo.

## 5. Métricas, Análises e Relatório

As métricas propostas nesse projeto foram:

- Taxa de retenção
- Número médio de pedidos por usuário
- Ticket médio
- Receita média por usuário

Obs.: 
- As análises realizadas se encontram nos notebooks "Analysis".
- **`Relatório.pdf`**: O arquivo ".pdf" que contém o relatório com as conclusões e sugestões.