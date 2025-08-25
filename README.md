# Classificação de Cogumelos com Aprendizado de Máquina  
*Uma Abordagem Baseada em Bioinformática*

---

## Objetivo do Projeto
Na prática, queremos responder à seguinte pergunta:

**Até que ponto é possível treinar modelos computacionais capazes de diferenciar cogumelos comestíveis de venenosos apenas com base em suas descrições físicas?**

Para isso, utilizamos uma abordagem de ciência de dados que envolve:  
- Explorar algoritmos de **classificação supervisionada** aplicados ao contexto micológico;  
- Comparar diferentes modelos quanto à sua **capacidade de generalização** frente à diversidade morfológica;  
- Avaliar o impacto de **decisões de pré-processamento** (ex.: tratamento de dados ausentes) na performance;  
- Refletir sobre as **limitações dos modelos e dos dados simulados**, além dos desafios reais na aplicação prática.  

Este projeto também tem caráter formativo e exploratório, com foco no aprendizado prático de **modelagem de dados, engenharia de atributos e avaliação de desempenho**.  
Nosso trabalho visa pavimentar o caminho para uma *etapa futura de construção de uma base de dados própria, voltada para fungos do gênero* **Funalia**, usando técnicas de curadoria e simulação baseadas em NLP.  

---

## Contexto e Motivação
O **Reino Fungi** possui uma biodiversidade impressionante, estimada em até **3,8 milhões de espécies**, das quais apenas ~100 mil foram oficialmente descritas.  
Apesar de sua relevância ecológica, médica e alimentar, a **classificação de fungos** ainda enfrenta grandes desafios, principalmente pela limitação dos métodos tradicionais de identificação morfológica.  

Exemplo: espécies morfologicamente semelhantes, como *Agaricus bisporus* (comestível) e *Agaricus xanthodermus* (tóxico), mostram o risco de erros e a necessidade de **alternativas automatizadas** para garantir segurança alimentar.  

---

## Dataset Utilizado
- **Mushroom Dataset (1987)**: um dos primeiros a ser usado em ML, disponível no UCI Repository. Simples demais, com poucas espécies, facilitando demais a tarefa dos modelos.  
- **Secondary Mushroom Dataset (Wagner et al., 2021)**: simula **61 mil cogumelos** a partir de descrições morfológicas reais de **173 espécies** do livro *Mushrooms and Toadstools* (Kibby, 1994).  

Optamos pelo **Secondary Mushroom Dataset** por oferecer **maior diversidade morfológica, complexidade e representatividade** dos desafios reais da classificação fúngica.  

---

## Pipeline de Ciência de Dados
O projeto foi estruturado em quatro etapas principais:

1. **Análise Exploratória**
   - Distribuições, padrões e valores ausentes  
   - Importância das variáveis  
   - Análise de dependência e relações entre atributos  

2. **Tratamento de Dados**
   - Remoção/imputação de variáveis com excesso de nulos  
   - Codificação de variáveis categóricas  
   - Padronização dos dados  

3. **Modelagem**
   - Algoritmos: **KNN, SVM (RBF) e Random Forest**  
   - Ajuste de hiperparâmetros via **GridSearchCV** com validação cruzada  

4. **Avaliação**
   - Métricas: **Acurácia, Precisão, Recall e F1-score (macro)**  
   - Interpretação dos erros e riscos de classificação  

---

## Principais Resultados
- **SVM (RBF kernel)** → melhor desempenho, com acurácia praticamente total.  
- **KNN** → resultados próximos ao SVM, eficiente em padrões locais.  
- **Random Forest** → boas métricas gerais, mas apresentou erros críticos (classificou cogumelos venenosos como comestíveis).  

Esse risco demonstra que, em aplicações reais, o modelo deve priorizar **minimizar falsos negativos** (classificar venenosos como comestíveis).  

---

## Próximos Passos
- Explorar novos algoritmos: **MLP, AdaBoost, QDA, Gaussian Naive Bayes**  
- Construção de um **dataset simulado próprio**, com foco em espécies do gênero *Funalia*  

---

## Estrutura do Repositório

secondary-mushroom-classifier/

│

├── data/                           # Conjunto de dados

│   ├── secondary_data.csv          # Dataset principal

│   └── secondary_data_meta.txt     # Metadados do dataset

│

├── notebook/                       # Notebooks de análise

│   ├── desktop.ini                 # Arquivo de configuração do Windows (pode remover)

│   └── secondary_mushroom.ipynb    # Notebook de classificação

│

├── LICENSE                         # Licença do projeto (MIT License)

└── README.md                       # Documentação principal do projeto
