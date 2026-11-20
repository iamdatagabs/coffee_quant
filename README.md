# Coffee_Quant

# ☕ Análise Quantitativa & Preditiva: Mercado de Café

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Statsmodels](https://img.shields.io/badge/Statsmodels-Time_Series-150458?style=for-the-badge)
![Plotly](https://img.shields.io/badge/Plotly-Interactive_Dashboard-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-Live_Demo-222222?style=for-the-badge&logo=github&logoColor=white)

Modelagem econométrica, financeira e de *Machine Learning* aplicada à série histórica de preços da saca de café, com projeção sazonal de 5 anos e visualização interativa na web.

🔗 **[Acesse o Dashboard Interativo Online](https://iamdatagabs.github.io/coffee_quant/)**

---

## 🎯 Objetivo e Metodologia

Diferente de abordagens lineares simples que ignoram a dinâmica agrícola, este projeto estrutura os dados em frequência mensal (`MS`) para capturar os ciclos de **safra e entressafra**, combinando três frentes analíticas:

1. **Séries Temporais & Machine Learning (Holt-Winters):**
   * Suavização Exponencial Tripla (`ExponentialSmoothing`) com tendência amortecida (`damped_trend=True`) e sazonalidade multiplicativa (`seasonal_periods=12`).
   * Validação cruzada temporal (*out-of-sample* nos últimos 12 meses) avaliada por **RMSE**, **MAE**, **MAPE** e **MASE** (*Mean Absolute Scaled Error*).
2. **Finanças Quantitativas & Gestão de Risco:**
   * Cálculo de retorno composto anual (**CAGR**), volatilidade anualizada ($\sigma\sqrt{12}$), **Índice de Sharpe**, **Drawdown Máximo** e **Value at Risk (VaR 95%)**.
3. **Macroeconomia & Elasticidade:**
   * Decomposição de ciclo e tendência estrutural via **Filtro Hodrick-Prescott** ($\lambda = 14400$).
   * Estimativa de contração implícita da demanda baseada na elasticidade-preço referencial da literatura para commodities agrícolas ($\varepsilon_d \approx -0.25$).

---

## 📂 Estrutura do Repositório

```text
├── index.html               # Dashboard interativo compilado (GitHub Pages)
├── analise_cafe.ipynb       # Notebook principal (ETL, modelagem e exportação)
├── preco_cafe.csv           # Base histórica de preços mensais
└── README.md                # Documentação do projeto
