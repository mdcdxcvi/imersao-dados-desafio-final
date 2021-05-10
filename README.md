[![colab](https://camo.githubusercontent.com/52feade06f2fecbf006889a904d221e6a730c194/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)](https://colab.research.google.com/github/mdcdxcvi/imersao-dados-desafio-final/blob/main/Notebooks/Vin%C3%ADcius_O_Romano_Silva.ipynb) [![sklearn](https://img.shields.io/badge/lib-scikit&#8208;learn-lightblue)](https://sklearn.org/) [![plotly](https://img.shields.io/badge/lib-plotly-darkblue)](https://plotly.com/) [![pandas](https://img.shields.io/badge/lib-pandas-white)](https://pandas.pydata.org/) [![matplotlib](https://img.shields.io/badge/lib-matplotlib-blue)](https://matplotlib.org/) [![numpy](https://img.shields.io/badge/lib-numpy-darkgreen)](https://numpy.org/) [![ipywidgets](https://img.shields.io/badge/lib-ipywidgets-orange)](https://ipython.org/)

![Modelando Mecanismos de Ação de Compostos](./Images/topo.png "Modelando Mecanismos de Ação de Compostos")
# Modelando Mecanismos de Ação de Compostos
#### Desafio Final Imersão Dados 3 💻 Alura 💜

## Introdução 📖

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Este trabalho demonstra os resultados da análise de um conjunto de dados de <i>Drug discovery</i>, tema da 3ª Imersão de Dados da Alura. O conjunto de dados integra o desafio <a href="https://www.kaggle.com/c/lish-moa"><i>Mechanisms of Action (MoA) Prediction</i></a>, proposto no <a href="https://www.kaggle.com/"><i>kaggle</i></a> como parte do projeto <a href="https://clue.io/"><i>ConnectivityMap</i></a>, onde é proposta à comunidade a busca por correlações relevantes que ajudem na previsão do comportamento dos mecanismos de ação para a classificação de drogas.</div>
&nbsp;

## O Projeto 📚

### Objetivo

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Elaborar um modelo que, selecionado uma proteína alvo presente no conjunto de dados, possa responder com uma lista de expressões gênicas (de <code>g-0</code> a <code>g-771</code>) e/ou expressões dos tipos de células (de <code>c-0</code> a <code>c-99</code>) que desperte diferentes mecanismos de ação sobre a proteína em questão. </div>

### Hipóteses

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; A ideia por trás do projeto era encontrar grupos dos conjuntos de dados com uma alta correlação, para assim modelar a inferência de um grupo dado o outro. </div>
&nbsp;

![DataFrame](./Images/df.png "DataFrame")

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Realizando diversos testes, surgiram evidências fortes que certos indicadores de expressões gênicas e de tipos de células aparentemente apresentavam  alta correlação uns com os outros (proporcional ou inversamente proporcional), como até mesmo os professores mostraram nas aulas.</div>
&nbsp;

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Partindo desta hipótese, elaborei com o apoio da <b><a href="https://sklearn.org/">biblioteca scikit-learn</a></b> um modelo baseado em Redes Neurais que prevesse resposta de certas expressões a partir de outras. Contudo, mesmo usando ferramentas para melhorar a performance do modelo com a busca de hiperparâmetros mais adequados ao problema, a acurácia não foi satisfatória, ficando na casa dos 60% no conjunto de teste, com resultados muito sensíveis a <i>overfitting</i>.</div>
&nbsp;

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Em seguida, explorei os dados relacionados aos mecanismos de ação dos compostos em proteínas alvo, do conjunto de dados de resultados. Por se tratarem de valores inteiros, pude modelar um classificador com a ferramenta de Árvore de Decisão.</div>
&nbsp;

### Estrutura

![DataFrame](./Images/arv.png "DataFrame")

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; O modelo é treinado para cada uma das proteínas alvo, usando como classes para o classificados os diferentes mecanismos de ação envolvidos. O algoritmo treina três modelos simultaneamente: o primeiro usa como entrada apenas as expressões gênicas; já segundo modelo é treinado com as expressões dos tipos de células; e, por fim, o último modelo é treinado com os dois tipos de expressões do conjunto de dados.</div>
&nbsp;

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Para esta modelagem tratei os dados do conjunto de resultados dos experimentos, de forma a alocar os mecanismos de ações em uma única coluna para cada <code>id</code> registrado, conforme abaixo. </div>
&nbsp;

![DataFrame](./Images/reações.png "DataFrame")

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Os modelos elaborados dessa forma obtiveram uma altíssima acuracia, tanto na fase de treinamento quanto na de teste, com resultados de acurácia raramente abaixo de 95%.</div>
&nbsp;

![DataFrame](./Images/arv_color.png "DataFrame")

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Para concluir o projeto, exibo um DataFrame que mostra os compostos envolvidos nos mecanimos de ação registrados. Assim, espero, ajudando a enteder o caminho entre o mecanismo de ação dos compostos, as alterações nas expressões gênicas e em diferentes tipos de células, e a relação destes mecanismos de ação com outros compostos do conjunto de dados.</div>
&nbsp;

![DataFrame](./Images/table.png "DataFrame")

### Conclusão

<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Com os resultados apresentados, concluo que:</div>

1. A modelagem dos dados com Árvore de Decisão é promissora para a classificação dos mecanismos de ação dos compostos em proteínas, apresentando uma acurácia próxima à 100%.
2. Tanto os indicadores das expressões gênicas, quanto as expressões dos tipos de células são excelentes parâmentros para a classificação e previsão dos mecanismos de ação em proteínas.
3. Para trabalhos futuros, sugiro o uso de maior poder computacional para explorar hiperparâmetros do modelo de Árvore de Decisão, para assim minimizar os indicadores de expressão necessários para a classificação correta do conjunto de dados.


<div style="text-align: justify"> &nbsp; &nbsp; &nbsp; Fico extremamente grato por todo o material disponibilizado e pela atenção dos professores na elaboração da imersão. 💜</div>
