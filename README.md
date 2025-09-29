# Desafio Técnico — Estágio em Machine Learning (Geofusion)

Este projeto foi desenvolvido como parte do processo seletivo da **Geofusion**, com foco em **análise exploratória de dados sociodemográficos** e construção de um **modelo de regressão** para previsão de faturamento em bairros do Rio de Janeiro.

---

## 📊 Objetivo

Dado um conjunto de variáveis sociodemográficas (população, faixas etárias, domicílios por classe social, renda média) e a variável de performance `faturamento`, o desafio consistiu em:

1. Explorar os dados e gerar **insights sobre o público-alvo**.
2. Criar um **modelo preditivo** capaz de estimar o faturamento em novos bairros.

---

## 📂 Estrutura do Projeto

* `Geofusion.ipynb` → Notebook principal com toda a análise, pré-processamento, modelagem e geração de relatório.
* `geofusion.py` → Versão em script Python, automatizada.
* `DesafioEstagioMachineLearning.csv` → Base de dados fornecida (não incluída neste repositório).
* `modelo_random_forest.pkl` → Modelo treinado salvo em formato `joblib`.
* `Relatorio_Executivo_Geofusion.pdf` → Relatório executivo com gráficos e previsões.

---

## 🔎 Análise Exploratória (EDA)

* Estatísticas descritivas e distribuição de variáveis.
* **Correlação de Pearson** para variáveis numéricas.
* **Cramér’s V** para associação entre variáveis categóricas.
* Criação de **flags de missing values** (ex.: `rendaMedia_missing`) para preservar informação de ausência.
* Identificação de **outliers** e tratamento via **capping IQR**.

**Principais insights:**

* `rendaMedia` e `população total` estão fortemente correlacionadas com o faturamento.
* Oportunidades de expansão foram identificadas em bairros com **alta renda média, mas baixo faturamento**.
* População adulta e domicílios de classes A e B aparecem como os mais relevantes para o desempenho.

---

## 🤖 Modelagem

Modelos testados:

* **Regressão Linear** (baseline).
* **Árvore de Decisão**.
* **Random Forest Regressor** (melhor resultado).

Métricas de avaliação:

* R² (coeficiente de determinação).
* RMSE (Root Mean Squared Error).
* MAE (Mean Absolute Error).

**Modelo escolhido:**
`Random Forest` com R² superior nos testes de validação cruzada (5-fold).

---

## 📈 Resultados

* Gráficos de **importância de variáveis** e **Real vs. Previsto**.
* Modelo salvo em `.pkl` para uso futuro.
* Previsão de faturamento para novos bairros simulados.
* Relatório executivo em PDF gerado automaticamente.

---

