# 🩺 Diagnóstico de Doenças Cardíacas (Grupo 3)

Este repositório contém o código-fonte e a análise de dados desenvolvidos para o projeto final da disciplina de Análise de Dados. O objetivo principal é estimar o risco de um paciente possuir doença arterial coronariana com base em dados clínicos coletados na triagem, apoiando a decisão médica para exames mais complexos[cite: 2, 5].

**Integrantes:**
* Luiz Henrique (Fases 1 e 2)
* Gustavo Tenório (Fase 3)
* Maycon C. (Fase 4)
* Renan Valença (Fase 5)[cite: 2]

---

## 📌 O Problema de Negócio
No ambiente de pronto-atendimento, é fundamental decidir rapidamente quais pacientes devem ser encaminhados para exames caros e demorados (como cateterismo ou angiotomografia)[cite: 2]. Este modelo de *Machine Learning* atua como um sistema de apoio, priorizando a redução de **falsos negativos** (pacientes doentes mandados para casa) através do foco em métricas de Sensibilidade (Recall) e ROC AUC[cite: 2].

## 📊 Sobre o Dataset
* **Origem:** [Kaggle - Heart Disease Dataset (johnsmith88)](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset)[cite: 2, 5].
* **Características:** 1025 registros originais e 13 variáveis de entrada (ex: pressão arterial, colesterol, angina, etc.)[cite: 2].
* **Variável Alvo:** `target` (0 = Saudável, 1 = Com doença cardíaca)[cite: 2, 5]. *(Nota: Os rótulos originais do Kaggle foram corrigidos durante a Análise Exploratória para garantir o alinhamento com a literatura médica)*[cite: 2].

## 🛠️ Metodologia e Etapas
O projeto foi desenvolvido em 5 fases[cite: 2, 3]:
1. **Carga e Definição:** Leitura dos dados e consolidação do problema de classificação binária[cite: 2, 3].
2. **Análise Exploratória (EDA):** Imputação de dados ausentes disfarçados pela moda (`ca` e `thal`), eliminação de vazamento de dados via remoção de duplicatas (70,5% do dataset) e análise de outliers biológicos[cite: 2, 3].
3. **Preparação dos Dados:** Divisão da base com a proporção 70/15/15 (Treino, Validação, Teste) com estratificação[cite: 2, 3]. Aplicação de balanceamento (*oversampling*) apenas na base de treino e normalização com `StandardScaler`[cite: 2, 3].
4. **Modelagem:** Treinamento dos algoritmos **Regressão Logística**, **Naive Bayes (GaussianNB)** e **Random Forest**[cite: 2, 4].
5. **Avaliação:** Extração de previsões de classe (*predict*) e probabilidade (*predict_proba*) para o cálculo de Acurácia, Precisão, Recall, Especificidade e ROC AUC[cite: 2, 4].

## 🏆 Resultados e Conclusão Final
Após avaliação no conjunto de Validação, o modelo **Random Forest** destacou-se por entregar a melhor taxa de Recall e a maior área sob a curva (ROC AUC)[cite: 4]. O teste com dados inéditos (conjunto de Teste) confirmou a eficácia do modelo para operar de forma robusta no pronto-atendimento, cumprindo o objetivo de minimizar a perda no diagnóstico de pacientes doentes[cite: 3, 4].
