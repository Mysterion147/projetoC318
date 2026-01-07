# Previsão de Atraso de Voo - Projeto de Aprendizagem Supervisionada

Este projeto tem como objetivo desenvolver um modelo preditivo capaz de identificar voos com alta taxa de atraso em aeroportos e companhias aéreas dos Estados Unidos, utilizando dados históricos da indústria aérea.

## 1. Contexto do Problema

O setor de aviação é altamente sensível à pontualidade. Atrasos geram custos operacionais elevados para as empresas e insatisfação para os passageiros. Prever quais rotas ou companhias estão sob maior risco permite um planejamento logístico mais eficiente e a adoção de estratégias de mitigação proativas.

### Objetivos de Negócio:
* Identificar quais companhias aéreas e aeroportos contribuem mais para o risco de atraso.
* Analisar a sazonalidade do risco de atraso ao longo do ano.
* Determinar quais variáveis são os preditores mais fortes para uma alta taxa de atraso.

## 2. Metodologia e Enquadramento

* **Tipo de Aprendizagem:** Supervisionada.
* **Tarefa:** Classificação Binária.
* **Variável Alvo:** `is_high_delay_rate` (1: Alto Risco, 0: Baixo Risco).
* **Definição do Alvo:** A variável foi criada com base na taxa de atraso mensal (`arr_del15 / arr_flights`). Foram classificados como "Alto Risco" os registros situados no quartil superior (top 25%) das maiores taxas de atraso.

## 3. Tecnologias Utilizadas

* **Linguagem:** Python
* **Manipulação de Dados:** Pandas, Numpy
* **Visualização:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn, XGBoost, LightGBM

## 4. O Dataset

O projeto utiliza o dataset `Airline_Delay_Cause.csv`, que contém registros detalhados sobre:
* Período (Ano e Mês).
* Identificação da Companhia Aérea e Aeroporto.
* Contagem de voos (totais, atrasados, cancelados, desviados).
* Causas específicas de atraso (clima, segurança, sistema aéreo, etc.).

## 5. Modelagem e Resultados

Foram testados três algoritmos de classificação:
1. Regressão Logística
2. XGBoost
3. LightGBM (LGBM)

### Principais Insights:
* **Sazonalidade:** Fatores temporais (ano e mês) mostraram-se os preditores mais fortes de risco, indicando forte influência de períodos como o inverno norte-americano e o cenário pós-pandemia.
* **Identidade da Companhia:** Empresas como SkyWest Airlines e Southwest Airlines apareceram como fatores de risco significativos na importância das features.
* **Análise Exploratória:** Companhias como JetBlue Airways, American Eagle Airlines e Frontier Airlines Inc apresentaram as maiores taxas médias de atraso no histórico analisado.

## 6. Como Executar o Projeto

1. Clone o repositório.
2. Certifique-se de ter o arquivo `Airline_Delay_Cause.csv` no diretório raiz.
3. Instale as dependências necessárias:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost lightgbm
4. Execute o notebook
