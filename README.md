# Explorando-Dados-Demogr-ficos-com-Servi-os-de-Big-Data-na-AWS

Para realizar o desafio de projeto e explorar o SQL no Amazon Athena, podemos seguir estes passos:

1. **Criar bucket no Amazon S3**:
   - Acesse o AWS Management Console e abra o console do Amazon S3²⁴.
   - No painel de navegação à esquerda, escolha 'Buckets'.
   - Selecione 'Create bucket' e insira um nome único para o bucket.
   - Escolha a Região da AWS onde deseja que o bucket resida.

2. **Criar Glue Crawler**:
   - No AWS Glue, selecione 'Crawlers' no menu do lado esquerdo⁹.
   - Clique em 'Create crawler' e siga as instruções para configurar o crawler.
   - Defina um nome para o crawler e especifique o caminho do S3 onde os dados estão armazenados.

3. **Criar aplicação no Amazon Athena**:
   - Defina o esquema e comece a executar consultas SQL usando o console do Amazon Athena¹.
   - Podemos criar um banco de dados e tabelas para organizar os dados.

4. **Criar tabelas**:
   - Use o comando `CREATE TABLE` no editor de consultas do Athena para definir a estrutura da tabela e o local dos dados no S3¹⁴.

5. **Eliminar recursos**:
   - Para eliminar recursos, podemos usar o comando `DELETE` no Athena para excluir linhas em tabelas do Apache Iceberg¹⁸.
   - Lembre-se de remover quaisquer buckets do S3 e crawlers do Glue que não serão mais utilizados.

6. **Visualizar dados no Amazon QuickSight**:
   - Conecte-se aos seus dados no QuickSight e crie visualizações e dashboards²⁸.
   - Podemos visualizar tabelas em um conjunto de dados e adicionar insights integrados com machine learning.

Para criar tabelas no Amazon Athena, podemos seguir estes passos:

1. **Abra o console do Amazon Athena**:
   - Acesse o [console do Amazon Athena](^1^).

2. **No editor de consultas**:
   - Ao lado de "Tables and views" (Tabelas e visualizações), escolha "Create" (Criar) e, em seguida, "S3 bucket data" (Dados do bucket do S3).

3. **Defina o esquema da tabela**:
   - Use o formulário para criar tabela ou execute uma instrução DDL no editor de consultas do Athena.
   - O comando `CREATE TABLE` é utilizado para definir a estrutura da tabela e o local dos dados no S3.

Aqui está um exemplo básico de como podemos criar uma tabela no Athena:

```sql
CREATE EXTERNAL TABLE IF NOT EXISTS database_name.table_name (
  column1_name column1_data_type COMMENT 'column1_comment',
  column2_name column2_data_type COMMENT 'column2_comment',
  ...
)
ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.lazy.LazySimpleSerDe'
WITH SERDEPROPERTIES (
  'serialization.format' = '1',
  'field.delim' = ',',
  'collection.delim' = 'undefined',
  'mapkey.delim' = 'undefined'
)
STORED AS INPUTFORMAT 'org.apache.hadoop.mapred.TextInputFormat'
OUTPUTFORMAT 'org.apache.hadoop.hive.ql.io.HiveIgnoreKeyTextOutputFormat'
LOCATION 's3://bucket_name/folder/';
```

Lembre-se de substituir `database_name`, `table_name`, `column1_name`, `column1_data_type`, `column2_name`, `column2_data_type`, e o caminho do bucket do S3 com os valores correspondentes aos seus dados.

Para mais informações detalhadas e exemplos, podemos consultar a [documentação oficial do Amazon Athena](^2^). 

https://github.com/cassianobrexbit/dio-live-athena

https://docs.google.com/presentation/d/1u1_Iw78F7TkIaV2dN3KfYiN6I--W6_1v/edit?usp=sharing&ouid=105780375946211087074&rtpof=true&sd=true
