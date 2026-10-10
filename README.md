📊 Dashboard de Análise de Recursos Humanos (Power BI & MySQL)

Projeto prático desenvolvido para o desafio de Processamento de Dados com Power BI do bootcamp da DIO (Digital Innovation One).

🎯 Objetivo do Projeto

O objetivo deste projeto foi realizar o processo de ETL (Extração, Transformação e Carga) a partir de um banco de dados relacional MySQL (azure_company), estruturar o modelo de dados relacional e construir um dashboard executivo e interativo no Power BI para análise de indicadores e métricas de Recursos Humanos.

⚙️ Tecnologias e Ferramentas Utilizadas

MySQL Server 8.0 & MySQL Workbench: Hospedagem, criação e gestão do banco de dados relacional local.

MySQL Connector/NET: Conectividade nativa entre a base de dados local e o Power BI Desktop.

Power Query: Limpeza, transformação, tipagem e mescla de consultas de dados.

Power BI Desktop: Modelagem relacional (Star Schema), criação de medidas DAX e design de interfaces.

Git & GitHub: Controlo de versão, alojamento do código, script SQL e documentação de portfólio.

🔄 Etapas de Tratamento e Transformação dos Dados (ETL)

Conexão com Banco Relacional: Estabelecida ligação segura do Power BI ao servidor local via localhost na base de dados azure_company.

Tratamento de Tipos e Cabeçalhos: Validação rigorosa dos tipos de dados (Texto, Datas, Inteiros e Decimais/Moeda) e promoção correta dos cabeçalhos das tabelas.

Mescla de Colunas: Unificação do primeiro (Fname) e último nome (Lname) dos colaboradores numa única coluna limpa (Colaborador).

Relacionamento e Mescla de Tabelas: Realizada a associação entre empregados, departamentos e gerentes através da operação de Mesclar (Merge).

Nota Técnica (Merge vs. Append):

Utilizamos a operação de Mesclar (Merge) porque ela funciona como um JOIN do SQL: combina duas tabelas horizontalmente, adicionando novas colunas com base em uma chave comum (como o ID do departamento). A operação de Acrescentar (Append) funciona como um UNION, empilhando novas linhas de dados que possuem exatamente a mesma estrutura (como juntar vendas de Janeiro e vendas de Fevereiro), o que não se aplica para cruzar informações de entidades totalmente diferentes.

Tratamento de Valores Nulos: Validação de chaves estrangeiras e da hierarquia de supervisão (Super_ssn).

📈 Métricas e Indicadores Criados (DAX)

As principais medidas DAX desenvolvidas para o relatório incluem:

Total de Colaboradores (Headcount):

Total Colaboradores = COUNTROWS('azure_company employee')


Massa Salarial Total:

Massa Salarial = SUM('azure_company employee'[Salary])


Média Salarial da Empresa:

Media Salarial Empresa = AVERAGE('azure_company employee'[Salary])


🎨 Estrutura e Funcionalidades do Dashboard

Cartões Executivos (KPIs): Visão rápida e resumida do Headcount total (8), Média Salarial (35.13K) e Massa Salarial (281.00K).

Gráfico de Colaboradores por Departamento: Distribuição quantitativa da força de trabalho nas áreas de Research, Administration e Headquarters.

Gráfico de Colaboradores por Gerente: Análise da amplitude de controle e alocação de equipas por liderança.

Tabela de Detalhe Individual: Listagem detalhada contendo Colaborador, Departamento, Salário, Supervisor/Gerente e Género.

Segmentação de Dados Dinâmica: Filtros interativos por Género (Sex) e Departamento (Dname).

🚀 Como Replicar este Projeto Localmente

Execute o script SQL da base de dados azure_company no seu servidor MySQL local.

Certifique-se de que tem o driver MySQL Connector/NET instalado no seu computador.

Abra o ficheiro .pbix do projeto no Power BI Desktop.

Atualize as credenciais de acesso à base de dados caso necessário (Transformar Dados > Configurações da Fonte de Dados).

👨‍💻 Autor

Desenvolvido por Gabriela Pereira das Neves no âmbito da jornada de transição e especialização em Dados e Tecnologia.

