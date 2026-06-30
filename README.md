# NPS-Preditivo-em-E-commerce
## Visão Geral do Projeto
Este projeto tem como objetivo analisar e prever clientes com alto risco de se tornarem detratores de NPS (Net Promoter Score) em um e-commerce.  

A proposta combina Análise Exploratória de Dados (EDA) com modelos de Machine Learning, buscando identificar os principais fatores operacionais que impactam qualidades na experiência do cliente.

[**Vídeo apresentando o projeto**](https://drive.google.com/file/d/1jK02KtOEIPRfrBEHhEHCt9XyR9t-owzY/view?usp=drive_link)

## Objetivo
  - identificar fatores que influenciam a insatisfação do cliente
  - Entender padrões de comportamento de detratores
  - Crie um modelo preditivo para classificar clientes em:
    - Detrator (NPS ≤ 6)
    - Não detrator (NPS > 6)
  - Gerar insights acionáveis ​​para melhoria da operação

## Estrutura do Projeto
projeto-nps
│
├── eda_spark.ipynb # Análise exploratória com Spark SQL
├── modelagem_ml.ipynb # Random Forest e Regressão Linear
├── dataset.csv # Base de dados
└── README.md # Documentação do projeto

## Conjunto de Dados
A base contém 2.500 registros e 19 variáveis, incluindo:

  - Dados de cliente (cidade, região, tempo de relacionamento)
  - Dados de pedido (valor, itens, desconto)
  - Indicadores logísticos (atraso, esforço de entrega)
  - Indicadores de suporte (contatos, solicitações, tempo de resolução)
  - Pontuação NPS (alvo variável)

## Preparação dos Dados

  - Remoção de variáveis ​​com risco de vazamento de dados:

    - pontuação nps
    - id_do_cliente
    - id_do_pedido
      
  - quilo da variável alvo:
    - é_detrator = 1 (NPS ≤ 6)
      
  - Codificação de variáveis ​​categóricas com Label Encoding

  - Engenharia de atributos com foco em risco operacional

## Análise Exploratória (EDA)
A análise foi realizada com Spark SQL, Pandas e Seaborn.

Principais insights:

  - 74% dos clientes são detratores
  - Atrasos acima de 3 dias aumentam fortemente a insatisfação
  - Mais de 3 contatos com suporte indicam alto risco de detratação
  - 5 ou mais reclamações representam nível crítico de insatisfação
  - Resolução acima de 10 dias reduz significativamente o NPS
  - Fatores operacionais têm impacto maior que fatores demográficos

## Pontos de ruptura Identificados

Fator	Ponto crítico	Impacto
Atraso de entrega	3+ dias	Forte aumento de detratores
Suporte	3+ contatos	Alto risco de insatisfação
Reclamações	5+	Nível crítico
Resolução	10+ dias	Queda significativa de NPS
