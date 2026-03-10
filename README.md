# pipeline-vendas-aws
🚀 Pipeline ETL automatizado: Extração de dados locais, tratamento com Python (Pandas) e carregamento em Data Lake AWS S3 com foco em segurança e resiliência.

# 🚀 Data Pipeline: Vendas Local to Cloud (AWS S3)

Este projeto simula um ambiente real de Engenharia de Dados, onde dados brutos de vendas são extraídos, tratados e carregados automaticamente em um Data Lake na nuvem (AWS).

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python 3.x
* **Manipulação de Dados:** Pandas
* **Cloud Storage:** AWS S3 (Simple Storage Service)
* **Integração Cloud:** Boto3 (SDK oficial da AWS)
* **Segurança:** Dotenv (para gestão de variáveis de ambiente)

## 🏗️ Arquitetura do Pipeline
1. **Extração:** Script lê arquivos `.csv` de uma pasta local de "Vendas Brutas".
2. **Transformação (ETL):** - Limpeza de valores nulos e duplicatas.
   - Tipagem de dados (garantindo que datas e valores monetários estejam corretos).
   - Adição de coluna de `data_processamento`.
3. **Carga (Load):** O arquivo limpo é enviado via API para um Bucket na **AWS S3** (`pipeline-vendas-yasmin`).

## 🛡️ Tratamento de Erros & Segurança
- **Resiliência:** O pipeline utiliza blocos `try/except` para capturar falhas de conexão com a AWS ou erros de permissão.
- **Segurança (Best Practices):** Nenhuma chave de acesso (Access Keys) está exposta no código. Todas as credenciais são lidas de um arquivo `.env` protegido por `.gitignore`.

## 📂 Como Rodar este Projeto
1. Clone o repositório.
2. Crie um ambiente virtual e instale os requisitos: `pip install -r requirements.txt`.
3. Configure seu arquivo `.env` com suas chaves AWS.
4. Execute `python src/pipeline.py`.

---
📊 *Projeto desenvolvido por Yasmin Lopes - Aspirante a Engenheira de Dados.*
