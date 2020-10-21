# Exercício de Engenharia de Dados

> Queremos que, a partir dos dados disponibilizados, você responda, de preferência com gráficos às
seguintes questões:
> 1. Qual a distância média percorrida por viagens com no máximo 2 passageiros;
> 2. Quais os 3 maiores vendors em quantidade total de dinheiro arrecadado;
> 3. Faça um histograma da distribuição mensal, nos 4 anos, de corridas pagas em dinheiro;
> 4. Faça um gráfico de série temporal contando a quantidade de gorjetas de cada dia, nos
últimos 3 meses de 2012.

## Reprodução
Para reproduzir a análise, basta clonar este repositório e executar o notebook `datasprints-eng-test.ipynb`.

Os dados foram importados no AWS RDS a partir do AWS S3 via AWS Glue.

#### Passos seguidos na etapa de ETL
- Criar um bucket no AWS S3 e importar o dataset
-  Criar um banco de dados publicamente acessível no AWS RDS (MySQL 5.5)
- Configurar o ETL no AWS Glue
  - Criar um classificador do tipo JSON com o path $[*]
  - Criar um AWS IAM Role com as políticas AmazonS3FullAccess e AWSGlueServiceRole
  - Criar e executar um crawler para o bucket do dataset
  - Criar conexão para o banco de dados AWS RDS
  - Realizar mapeamento de colunas e tipos
  - Executar job
