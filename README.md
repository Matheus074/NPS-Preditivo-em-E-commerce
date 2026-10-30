# 📊 NPS Preditivo em E-commerce

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![PySpark](https://img.shields.io/badge/Spark%20SQL-E25A1C?logo=apachespark&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)

Análise e previsão de clientes com **alto risco de se tornarem detratores de NPS** (Net Promoter Score) em um e-commerce.

O projeto combina **Análise Exploratória de Dados (EDA)** com **Machine Learning** para identificar quais fatores operacionais mais pesam na experiência do cliente, e em que ponto eles passam a gerar insatisfação.

🎥 [**Vídeo de apresentação do projeto**](https://drive.google.com/file/d/1jK02KtOEIPRfrBEHhEHCt9XyR9t-owzY/view?usp=drive_link)

## 🎯 Objetivos

- Identificar os fatores que influenciam a insatisfação do cliente
- Entender os padrões de comportamento dos detratores
- Construir um modelo preditivo que classifique o cliente em:
  - **Detrator** (NPS ≤ 6)
  - **Não detrator** (NPS > 6)
- Gerar insights acionáveis para melhorar a operação

## 💡 Principais resultados

| Fator | Ponto crítico | Impacto |
|---|---|---|
| Atraso na entrega | 3 dias ou mais | Forte aumento de detratores |
| Contatos com o suporte | 3 ou mais | Alto risco de insatisfação |
| Reclamações | 5 ou mais | Nível crítico de insatisfação |
| Tempo de resolução | 10 dias ou mais | Queda significativa do NPS |

**Conclusão:** fatores **operacionais** (logística e atendimento) têm impacto maior no NPS do que fatores **demográficos**. Atacar atrasos e reincidência no suporte é a alavanca mais direta para reduzir detratores.

<!--
## 🤖 Desempenho do modelo
(Preencha com os números do notebook e remova este comentário para a seção aparecer no GitHub.)

| Modelo | Recall (detrator) | Precisão | F1 | AUC |
|---|---|---|---|---|
| Random Forest | | | | |
| Regressão ___ | | | | |

Como 74% da base são detratores, explique aqui como tratou o desbalanceamento
(ex.: class_weight, ajuste de threshold, estratificação no split).

![Matriz de confusão](imagens/matriz_confusao.png)
-->

## 🗂️ Conjunto de dados

A base tem **2.500 registros** e **19 variáveis**, agrupadas em:

- **Cliente:** cidade, região, tempo de relacionamento
- **Pedido:** valor, quantidade de itens, desconto
- **Logística:** atraso, esforço de entrega
- **Suporte:** contatos, solicitações, tempo de resolução
- **Alvo:** nota de NPS

## 🧹 Preparação dos dados

- Remoção de variáveis com risco de **vazamento de dados**: a própria nota de NPS e os IDs de cliente e de pedido
- Criação da variável alvo: detrator = 1 quando NPS ≤ 6
- Codificação de variáveis categóricas com **Label Encoding**
- Engenharia de atributos com foco em **risco operacional**

## 🔍 Análise exploratória

Feita com **Spark SQL**, **Pandas** e **Seaborn**. Destaques:

- **74%** dos clientes da base são detratores
- Atrasos acima de 3 dias aumentam fortemente a insatisfação
- Mais de 3 contatos com o suporte indicam alto risco de detração
- 5 ou mais reclamações representam nível crítico de insatisfação
- Resoluções acima de 10 dias reduzem significativamente o NPS

## 📁 Estrutura do projeto

```
.
├── eda_spark.ipynb      # Análise exploratória com Spark SQL
├── modelagem_ml.ipynb   # Modelagem: Random Forest e Regressão Linear
├── dataset.csv          # Base de dados
└── README.md
```
<!-- Conferir: se o segundo modelo foi Regressão Logística (classificação), ajuste o nome acima e na tabela de desempenho. -->

## 🚀 Como executar

```bash
pip install pyspark pandas seaborn scikit-learn jupyter
jupyter notebook
```

Abra `eda_spark.ipynb` para a análise exploratória e depois `modelagem_ml.ipynb` para a modelagem.

## 👤 Autor

**Matheus Cadoni** · [LinkedIn](https://www.linkedin.com/in/matheus-cadoni-aab94a208) · [GitHub](https://github.com/Matheus074)
