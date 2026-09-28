# Mlp-Som-Seoul-bike-renting
Projeto para MLP e SOM sobre aluguel de bicicletas na capital de Seoul. Tem com objetivo prever quantas bicicletas são alugadas por hora por variáveis preditoras como o clima

## Estrutura

| Arquivo | Conteúdo |
|---|---|
| `SeoulBikeData.csv` | dataset original (backup, nunca sobrescrito) |
| `preprocessing.ipynb` | limpeza inicial: remove `Functioning Day = No` e cria `IsWeekend` |
| `SeoulBikeData_treated.csv` | saída do pré-processamento, entrada dos dois notebooks seguintes |
| `mlp_seoul_bike.ipynb` | trabalho de MLP: holdout, validação cruzada, Random Search, TPE, sensibilidade individual e teste final |
| `som_seoul_bike.ipynb` | trabalho de SOM: mapa auto-organizável, U-Matrix, Hit Map, mapas de componentes, regiões e erros da MLP por BMU |

## Como executar

```bash
python -m venv venv
venv/Scripts/pip install -r requirements.txt
```

Ordem: `preprocessing.ipynb` → `mlp_seoul_bike.ipynb` → `som_seoul_bike.ipynb`. O notebook de SOM reconstrói a MLP final para relacionar seus erros ao mapa e confere (`assert`) que o RMSE de teste é o mesmo do notebook de MLP.
