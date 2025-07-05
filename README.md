# Modelo de Churn com XGBoost e Otimização via Optuna

Este projeto implementa um pipeline completo de machine learning para previsão de **churn (evasão de clientes)**, com foco em **modelos robustos de classificação**, especialmente o **XGBoost**, e uso avançado de **Optuna** para otimização automática de hiperparâmetros.

---

## Objetivo

Identificar quais clientes possuem maior probabilidade de deixar um serviço (churn) utilizando dados históricas e técnicas de machine learning

---

## Libs e Algoritmos Utilizados

- Python 3.x  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- XGBoost
- Optuna
- LightGBM
- Regressão Logística
- Random Forest

---

## Pipeline do Projeto

1. **Carregamento e análise exploratória dos dados (EDA)**
2. **Pré-processamento**
   - Tratamento de nulos
   - Encoding de variáveis categóricas
   - Normalização/Escalonamento
3. **Divisão em treino e teste**
4. **Modelagem supervisionada**
   - Avaliação de múltiplos algoritmos
   - Otimização de hiperparâmetros com **Optuna**
5. **Validação cruzada com métricas robustas**
6. **Comparação e seleção final de modelos**

---

## Otimização com Optuna

Utilizei a biblioteca **Optuna** para buscar os melhores hiperparâmetros de diferentes modelos de classificação, explorando combinações automaticamente com base na métrica AUC (Area Under the ROC Curve).  

Essa abordagem permitiu atingir **performance próxima do ideal (AUC → 1.00)** em validação cruzada, de forma automatizada e reproduzível.

---

## Métricas de Avaliação

A performance dos modelos foi avaliada com base nas seguintes métricas:

- **AUC-ROC** (principal critério de otimização, pois para churn, é importante que o modelo possa classificar bem independente do thresold)
- **Matriz de Confusão**

Essas métricas foram medidas tanto no conjunto de validação quanto no teste final, garantindo generalização.

---

## Modelo Principal: XGBoost

Após comparação entre diferentes algoritmos, o **XGBoost** foi escolhido como modelo final por apresentar:

- Melhor desempenho em AUC
- Boa capacidade de generalização
- Robustez a dados desbalanceados
