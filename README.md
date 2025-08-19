# ChallengeAluraTelecomX

# Relatório

Este relatório descreve o passo a passo das etapas de extração e transformação realizadas nos dados para posteriormente ser feita uma análise exploratória para descobrir possíveis razões de Churn da empresa Telecom X

### Extração

  * Importação das bibliotecas `pandas`, `matplotlib.pyplot` e `seaborn`.
  * Definição do URL para o arquivo JSON (`TelecomX_Data.json`).
  * Leitura dos dados do URL utilizando `pd.read_json()` e armazenamento no DataFrame `dados`.
  * Exibição das primeiras linhas do DataFrame `dados` para inspeção inicial.

### Transformação

 * Normalização das colunas aninhadas (`customer`, `phone`, `internet`, `account`) utilizando `pd.json_normalize()`.
 * Criação de DataFrames separados para cada coluna normalizada: `customer_normalized`, `phone_normalized`, `internet_normalized`, `account_normalized`.
 * Remoção das colunas aninhadas originais do DataFrame `dados` para criar `dados_flat`.
 * Concatenação horizontal (`axis=1`) do `dados_flat` com os DataFrames normalizados para criar o DataFrame `dados` unificado.
 * Configuração da opção de exibição do pandas para mostrar todas as colunas (`pd.set_option('display.max_columns', None)`).
 * Exibição do DataFrame `dados` completo após a normalização e concatenação.

 * Criação de uma nova coluna chamada `Contas_diarias`.
 * Cálculo dos valores para a coluna `Contas_diarias` dividindo os valores da coluna `Charges.Monthly` por 30 e arredondando para duas casas decimais.
 * Exibição do DataFrame `dados` com a nova coluna `Contas_diarias`.

 * Cálculo da contagem e percentual de valores nulos (`isnull().sum()`) para cada coluna do DataFrame `dados`.
 * Cálculo da contagem e percentual de valores vazios (`astype(str).apply(lambda x: x.str.strip() == '').sum()`) para cada coluna do DataFrame `dados`.
 * Criação de um DataFrame resumo (`summary_df`) com as contagens e percentuais de nulos e vazios.
 * Filtragem do DataFrame resumo (`summary_df_filtered`) para mostrar apenas as colunas que possuem contagem de nulos ou vazios maior que zero.
 * Exibição do DataFrame `summary_df_filtered`.

 * Identificação das linhas no DataFrame `dados` onde a coluna 'Churn' contém valores vazios ('').
 * Exibição das linhas identificadas com valores vazios na coluna 'Churn'.

 * Identificação das linhas no DataFrame `dados` onde a coluna 'Charges.Total' contém valores vazios ('').
 * Exibição das linhas identificadas com valores vazios na coluna 'Charges.Total'.

 * Identificação de linhas duplicadas no DataFrame `dados` utilizando o método `duplicated(keep=False)`.
 * Exibição das linhas duplicadas encontradas ou uma mensagem indicando que não há duplicatas.

 * Substituição global dos valores "Yes" por 1 e "No" por 0 em todo o DataFrame `dados` utilizando o método `replace()`.
 * Exibição das primeiras linhas do DataFrame `dados` após a substituição.

Este relatório resume as principais ações realizadas nas etapas de extração e transformação dos seus dados.
