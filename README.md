# investimentos-ML

Projeto de Machine Learning aplicado a investimentos: previsão dos **proventos (dividendos) anuais** recebidos com modelos de regressão.

## O que o notebook faz

1. Carrega o histórico de proventos anuais (2020–2026) a partir de `data/2020_2026_proventos_anuais.xlsx`.
2. Seleciona o período de treino **2021–2025** (anos completos e representativos).
3. Treina dois modelos com `scikit-learn`:
   - **Linear** — `LinearRegression` sobre os valores brutos.
   - **Exponencial** — `LinearRegression` sobre `log(proventos)`, com `exp()` aplicado às previsões.
4. Compara os modelos com **R²**, **MAPE** e **RMSE**.
5. Projeta os proventos para **2026–2030** e o valor mensal médio esperado.
6. Valida a projeção de 2026 com o valor parcial já recebido no ano.

## Estrutura

```
.
├── data/                                 # planilha local (não versionada)
├── notebook.ipynb                        # análise e modelos
└── requirements.txt
```

## Como executar

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# Linux / macOS
source .venv/bin/activate

pip install -r requirements.txt
```

Crie a planilha `data/2020_2026_proventos_anuais.xlsx` (ela não está no repositório por conter dados pessoais) com as colunas:

| Ano  | Proventos Recebidos (R$) |
|------|--------------------------|
| 2021 | 1000.00                  |
| ...  | ...                      |

Depois abra o `investimento.ipynb` no VS Code ou Jupyter e selecione o kernel do `.venv`.

## Tecnologias

Python 3.12 · pandas · NumPy · scikit-learn · Matplotlib · seaborn
