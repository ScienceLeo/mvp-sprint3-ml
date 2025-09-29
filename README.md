# MVP PUC-Rio — Sprint 3 (Machine Learning & Analytics)
**Tema:** Previsão de Consumo de Energia (séries temporais)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ScienceLeo/mvp-sprint3-ml/blob/main/MVP_PUC_Rio_Previsao_Consumo_Energia.ipynb)

## Como executar
1. Clique no botão **Open in Colab** acima.
2. No Colab, vá em **Runtime > Run all** (Executar tudo).
3. O notebook lê o dataset via URL e gera automaticamente a pasta `artefatos_mvp/` com modelos (.pkl), métricas, predições e interpretabilidade.
4. Tempo total de execução: ~4 minutos.

## Estrutura do repositório
- `MVP_PUC_Rio_Previsao_Consumo_Energia.ipynb` — notebook final do MVP (único arquivo exigido na entrega).
- `data/` — pasta para hospedar dataset.
- `README.md` — este guia rápido.
- `artefatos_mvp/` — **gerada automaticamente** quando o notebook roda (não precisa estar versionada).

## Observações rápidas
- **Split temporal** (Treino → Validação → Teste) com **anti-leakage**: lags e médias móveis **causais** (`shift(1)`).
- **Modelos comparados:** Naïve, Ridge, Random Forest, HistGradientBoosting (default e tunado).
- **Resultados consolidados:** Tabela (Validação e Teste) + tempos de treino/inferência (seção 5.6 do notebook).
- **Campeão:** HGB (default), por menor **RMSE em Teste**.
- **Artefatos salvos:** modelos `.pkl`, predições de Val/Test, `permutation_importance_*`, `x_cols.json`, `metadata.json`.

## Reprodutibilidade
- Seeds e `random_state` definidos.
- Execução **fim a fim** no Colab, com leitura de dados por URL.
- Ao final, os artefatos ficam em `artefatos_mvp/` para auditoria e reuso.

## Licença
MIT — ver arquivo `LICENSE`.
