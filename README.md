📊 ETL - Análise de Contratos Quitados 
Este repositório contém um notebook Python que executa um pipeline de ETL (Extração, Transformação e Consulta) sobre uma base de dados de contratos quitados, utilizando dados hospedados em uma planilha do Google Sheets.

O foco principal está na exploração de métricas relacionadas a descontos aplicados, percentual de quitação, consultores, bancos e localização geográfica dos contratos.

🚀 Tecnologias Utilizadas
Python 3

Google Colab

gspread (integração com Google Sheets)

pandas

pandasql (consultas SQL sobre DataFrames)

🔍 Etapas do Processo ETL
1. Extração dos Dados
A planilha é acessada diretamente por meio da API do Google Sheets com autenticação via google.colab.auth. O worksheet chamado "QUITADOS" é carregado para um DataFrame pandas.

python
Copiar
Editar
worksheet = spreadsheet.worksheet('QUITADOS')
df = pd.DataFrame(worksheet.get())
2. Transformação
Primeira linha definida como cabeçalho.

Remoção de colunas desnecessárias (CONTRATO, colunas vazias ou sem nome).

Conversões para permitir análise quantitativa (como tratar %).

3. Consultas com SQL
Utilizando o pandasql, foram executadas várias consultas SQL sobre o DataFrame para obter insights importantes:

Exemplos de consultas realizadas:
🔝 Top 10 maiores descontos aplicados

📈 Contratos com percentual de desconto entre 70% e 80%

📊 Distribuição por situação do contrato (SITUAÇÃO)

🧑‍💼 Quantidade de contratos por CONSULTOR, RESPONSÁVEL, ESCRITÓRIO

🏦 Média percentual de desconto por BANCO

📍 Total de contratos por UF (estado)

📂 Estrutura do Arquivo
bash
Copiar
Editar
etl_16_06_2025.py  # Script principal com todas as etapas do processo
✅ Como Executar
Este projeto foi desenvolvido no Google Colab, mas pode ser adaptado para execução local com:

bash
Copiar
Editar
pip install gspread pandas pandasql
Certifique-se de:

Ter permissões adequadas para acessar a planilha Google.

Atualizar a spreadsheet_key se for usar sua própria planilha.

📌 Observações
Este script foi criado com objetivo exploratório e pode ser ajustado para se transformar em um pipeline de produção ou dashboard interativo (ex: com Streamlit).

Os dados utilizados são sensíveis e não estão incluídos neste repositório por questões de privacidade.

✍️ Autor
Pablo Paiva
