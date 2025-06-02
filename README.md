
# Descrição da Base de dados:

<div style = "text-align:justify;">&ensp;&ensp;A base de dados "Heart Disease" do UCI Machine Learning Repository tem como objetivo prever a presença de doenças cardíacas em pacientes. Contém registros multivariados com 303 instâncias e originalmente 76 atributos, mas as pesquisas utilizam um subconjunto de 14 atributos, dos quais 13 são características preditivas e 1 é a variável alvo (target). A classe alvo representa a presença (valores 1 a 4) ou ausência (valor 0) de doença cardíaca. As características são numéricas (inteiras e reais) e categóricas. A base possui valores ausentes em alguns atributos.</div>

◦ Pré-processamento e seleção de características:

Pré-processamento:
- Remoção de instâncias com valores ausentes ou substituição por média/mediana (imputação).
- Normalização dos dados contínuos com MinMaxScaler ou StandardScaler.
- Codificação de atributos categóricos com OneHotEncoder ou LabelEncoder.

Seleção de características:
- Uso do método *SelectKBest* com teste estatístico (ex: chi²) para selecionar as características mais relevantes.
- Alternativamente, aplicação de *análise de importância de atributos* com uma árvore de decisão ou modelo de floresta aleatória.

Atributos mais relevantes geralmente incluem:
- cp (tipo de dor no peito),
- thalach (frequência cardíaca máxima alcançada),
- exang (angina induzida por exercício),
- oldpeak (depressão ST induzida por exercício),
- ca (número de vasos principais com coloração),
- thal (tipo de talassemia).

◦ Classificadores:
Serão utilizados dois algoritmos de classificação:
1. *SVM (Support Vector Machine)*
	- É eficaz em espaços de alta dimensão e com margens bem definidas.
	- Pode usar diferentes funções kernel (linear, RBF) para ajustar a fronteira de decisão.
		
2. *Árvore de Decisão (Decision Tree)*
	- Interpretação simples e visualização da lógica de decisão.
	- Identifica automaticamente os atributos mais relevantes.


◦ Avaliação dos classificadores:
Serão utilizadas três métricas de desempenho:

1. *Acurácia* – Proporção de previsões corretas entre todas as previsões.
2. *Precisão* – Proporção de verdadeiros positivos entre os positivos previstos.
3. *Recall (Sensibilidade)* – Proporção de verdadeiros positivos entre todos os positivos reais.

A avaliação será feita com *validação cruzada k-fold (k=5)* para garantir robustez estatística dos resultados.
