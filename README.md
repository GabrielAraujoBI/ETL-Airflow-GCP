# MarketPulse Data Pipeline

Este projeto é um pipeline de dados construído com **Apache Airflow**, utilizando a distribuição da **Astronomer**, e integrando com **Google Cloud Storage (GCS)** e **BigQuery**.

## 🎯 Objetivo - Realizar a leitura, o tratamento e a ingestão de dados no GCP (Google Cloud Platform)

1. Leitura e tratamento do CSV de produtos de e-commerce utilizando Python e pandas;
2. Upload do CSV tratado para o GCS;
3. Criação do dataset no BigQuery;
4. Carregamento do arquivo do bucket para uma tabela no BigQuery usando Astro SDK (`aql.load_file`).

## 🛠️ Tecnologias e ferramentas

- Apache Airflow (via Astronomer)
- Python / pandas
- Astro SDK (Astro CLI + aql)
- Google Cloud Platform (GCS e BigQuery)
- Docker (ambiente local via Astronomer CLI)**

## ▶️ Como rodar localmente

1. Execute o Docker e inicie o ambiente local do Airflow com Astronomer
2. astro dev start
3. Acesse o Airflow Web UI em: http://localhost:8080
    3.1 Login: admin / Senha: admin
4. Configure a chave de serviço do google em Admin › Connections
   4.1 Preencha os campos:
                          **Conn Id:** = gcp
                          **Conn Type:** = Google Cloud
                          **Keyfile Path:** = Caminho local do seu **service_account.json** (ex: /usr/local/airflow/include/gcp/service_account.json)
                          💡Recomendação: mantenha esse arquivo fora do versionamento (.gitignore).
5. Execute a DAG
