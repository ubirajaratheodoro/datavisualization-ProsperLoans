# Udacity Projeto P6 - Faça Visualização de Dados Eficazes

# 1. Requisitos
A descrição completa dos requisitos do projeto estão disponíveis no arquivo: "Requisitos Udacity Projeto P6 - Faça Visualização de Dados Eficazes.pdf"

# 2. Resumo
Este projeto utilizará como ponto de partida a "SESSÃO DE GRÁFICOS FINAIS" - conforme reportado no arquivo prosperLoanData.html - e o dataset "ProsperLoanDataResume.csv", ambos resultantes das atividades de análise e exploração dos dados realizadas no projeto 4 da Udacity: "Explore e Resuma os Dados". 

Desta forma, utilizaremos as metodologias aplicáveis para uma visualização eficaz, dinâmica e interativa com base nos seguintes gráficos já apresentados na "SESSÃO DE GRÁFICOS FINAIS" do projeto 4 (disponível em https://goo.gl/6n8Kpu):
- "Evolução do Volume de Transações": Analisa o volume de transações ao longo do tempo
- "DebtToIncomeRatio do mutuário x Juros aplicados": Analisa a relação entre as condições de crédito do mutuário e as taxas de juros aplicadas aos empréstimos
- "Retorno por Volume de Transação": Analisa o retorno da financeira nas transações realizadas

Nosso objetivo neste projeto é, portanto, procurar reunir o máximo das informações apresentadas nestes 3 gráficos em um único gráfico dinâmico e interativo.

# 3. Design
- Diagnóstico inicial e definição do escopo: Conforme consta na documentação do projeto utilizado conforme item anterior, o primeiro gráfico serve para contextualização do cenário; o segundo foca mais diretamente na questão à ser respondida; e o terceiro por sua vez procura analisar os resultados efetivos da operação. Foram levantados todos os atributos utilizados nos 3 gráficos e optou-se na elaboração de um novo gráfico que pudesse sintetizar de maneira eficaz as informações dos gráficos 1 e 2. O terceiro gráfico foi excluído do escopo, pois conclui-se que a aumentaria muito a complexidade do modelo para exibir de maneira eficaz todas as informações dos 3 gráficos.

- Versão 1, definição de design 1 - Eixos do gráfico e Posicionamento: Verificou-se que a questão a ser respondida envolvia essencialmente a relação entre o atributo Taxa de Comprometimento da Renda (DebtToIncomeRatio) e o atributo Taxa de Juros Anual (BorrowerAPR). Concluiu-se assim que o posicionamento destes atributos no gráfico seria prioridade onde, então, atribuímos estes aos eixos X e Y respectivamente.

- Versão 1, definição de design 2 - Volume de Emprestimos(LoanAmount): O volume de empréstimos é o atributo que na verdade determinará ou não a forma de relação entre os atributos acima. Por isso, apresentamos o mesmo em forma de bolha, dimensionando seu diâmetro de acordo com o volume em cada posição x,y (DebtToIncomeRatio, BorrowerAPR). O objetivo foi o de procurar dar uma ideia desta relação inicialmente somente visualmente por meio da dimensão das bolhas, sem apresentação de números, desta relação.

- Versão 1, definição de design 3 - Evolução analítica: Um recurso importante que acredita-se ser essencial é poder visualizar também uma visão "analítica" de um determinado ponto do gráfico. Desta forma, ao parar com o mouse sobre uma bolha, é exibido então o valor total (que determinou o tamanho da bolha) e a evolução daquele ponto x,y ao longo do tempo.

- Versão 1, definição de design 4 - Panorama geral: Um ponto importante foi o de procurar dar uma visão geral sobre o negócio em si, ou seja, empréstimos. Por isso, optou-se por mostrar um gráfico de barras lateral com a evolução do volume total de empréstimos realizados ao longo do tempo. Essa visão permanece sempre visível ao gráfico, de forma à proporcionar uma comparação imediata visual entre uma visão analítica de um determinado ponto x,y e o total geral.

- Versão 1, definição de design 5 - Evolução do Público-segmentado: Juntamente com a definição de design 3, verificou-se importante também apresentar o total de volume de empréstimo por segmentação do público. Ou seja, verificou-se que para ponto x do gráfico (DebtToIncomeRatio) representa também um segmento de público que são os mutuários do empréstimos. Por isso, quando o mouse para sobre uma das bolhas, também é atualizado o gráfico de barras lateral, acrescentando o volume total de empréstimos ao longo do tempo para a taxa de comprometimento da renda selecionada (ponto x).

- Versão 2, definição de design 6 - Remoção das cores: Com base nos feedbacks recebidos e também de acordo com as melhores práticas para visualização eficaz de dados, verificou-se que o uso de cores implica também na associação com alguma legenda (o que não existia). Desta forma, adotou-se o padrão monocromático.

- Versão 2, definição de design 7 - Remoção do gráfico lateral de barras: Também com base nos feedbacks, conclui-se que a interação entre o gráfico tooltip da bolha selecionada e o gráfico lateral de barras não é tão intuitivo quanto se imaginava. Por isso, o gráfico lateral de barras foi incorporado ao tooltip, permitindo uma comparação no mesmo gráfico.

# 4. Feedback
Cada versão do gráfico produzida foi submetida à avaliação de pessoas de relacionadas à área de TI e relacionadas ao curso de analista de dados da Udacity por meio da plataforma slack. Abaixo apresentamos a relação dos feedbacks recebidos:

- Versão 1, Feedback 1: "Para min ficou claro isso, acho que o gráfico hint do ponto ficou muito bem detalhado, e traz uma ideia de linha de tempo boa. Uma coisa que eu achei falta foi quando seleciono um ponto no gráfico , tu pinta proporcionalmente o gráfico de volume de empréstimos por ano, porém eu não sei qual é o valor que isso representa e esse valor por ano não é mostrado em nenhum momento, apesar de ajudar a verificar uma tendência, isso senti falta. Já que tu tem o valor total do ano passando o mouse sobre o total do ano e tem indicado a proporcionalidade, ao final da barra quando seleciono um ponto poderia mostrar qual o valor do volume de empréstimos."

- Versão 1, Feedback 2: "Minha percepção é a seguinte: cruzar três ou mais variáveis em um gráfico único sempre é um desafio. No caso do exemplo proposto, temos a taxa de comprometimento de renda, a taxa de juros e o total de volume de empréstimos. Como tenho uma certa experiência com análise de dados e BI, não tive maiores dificuldades para compreender e assimilar as informações providas pelo gráfico. Achei bacana a interatividade do modelo, que mostra um mini-gráfico evolutivo e atualiza o gráfico de barras lateral quando posicionamos o mouse sobre um dos pontos do gráfico. Porém, entendo que a dificuldade maior de compreensão se apresentará justamente para quem não possui muita familiaridade com a interpretação de gráficos e elementos de estatística. Noto que infográficos de jornal ou revista, onde quem apresenta o material não consegue explicar pessoalmente o que está querendo se demonstrar no gráfico, costuma-se utilizar um formato mais tradicional de gráfico (com dois eixos apenas, normalmente gráficos de barra ou pizza). Em resumo, entendo que a solução proposta com este modelo de gráfico é eficaz, mas exige uma certa aptidão do leitor para uma compreensão maior."

- Versão 1, Feedback 3: "Curti @bira, principalmente a interação quando passa o mouse nas bolhas. Apenas as cores das bolhas parecem ser informação redundante da Taxa de Comprometimento da Renda (DebtToIncomeRatio), que já é informado no eixo X."

- Versão 1, Feedback 4: "Bem interessante, mas tem duas coisas que, no meu ponto de vista, poderiam melhorar. A coluna de barras horizontais não deveria ser crescente de baixo para cima, ao invés de decrescente? De 0.1 a 0.6 não entendi exatamente o que são cada coluna, talvez uma legenda adicional informando o que é cada coluna possa ajudar no sentido de bater o olho e já entender do que se trata."

- Versão 1, Feedback 5: "Apresenta fácil visualização e interpretação de dados. A funcionalidade dos valores com o cursor é uma vantagem positiva, pois evita a poluição de dados, levando o analista a considerar cada um de maneira individual para uma tomada de decisão. A questão das cores escolhidas para o gráfico tem alguma justificativa? Talvez uma legenda com o significado das cores
considerando que 80% das pessoas são visuais. Eu sou cinestésica, mas como contribuição uma legenda com as cores."

# 5. Recursos utilizados:
Neste projeto foram utilizadas as seguintes fontes de informação:

- http://www.perceptualedge.com/articles/visual_business_intelligence/rules_for_using_color.pdf
- http://www.thefunctionalart.com/p/about-book.html
- https://classroom.udacity.com/nanodegrees/nd002/parts/00213454010/modules/318423863275460/lessons/3063188874/concepts/31859788930923
- https://classroom.udacity.com/nanodegrees/nd002/parts/00213454010/modules/318423863275460/lessons/3063188874/concepts/33073888680923
- http://vita.had.co.nz/papers/tidy-data.pdf
- http://www.instantr.com/2012/12/11/exporting-a-dataset-from-r/
- https://hackernoon.com/visualizing-data-in-javascript-with-d3-js-and-dimple-7395681c4b74
- https://www.endpoint.com/blog/2015/10/15/intro-to-dimplejs-graphing-in-6-easy
- https://www.mkyong.com/html/html-tutorial-hello-world/
- https://www.w3.org/wiki/The_web_standards_model_-_HTML_CSS_and_JavaScript
- http://tableless.github.io/iniciantes/manual/js/inserindo-js.html
- https://www.w3.org/wiki/How_does_the_Internet_work
- http://tableless.github.io/iniciantes/
- https://www.w3.org/community/webed/wiki/The_web_standards_model_-_HTML_CSS_and_JavaScript
- https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element
- http://cavas.com.br/programacao/aplicativo-web-em-3-camadas/
- https://pt.slideshare.net/FabioMouraPereira/desenvolvimento-de-sistemas-web-conceitos-bsicos
- https://pt.stackoverflow.com/questions/8843/por-que-usar-javascript-se-existem-tantas-outras-tecnologias-para-gera-conte%C3%BAdo
- http://www.c-sharpcorner.com/UploadFile/2072a9/client-side-vs-server-side-programming-languages/
- https://github.com/PMSI-AlignAlytics/dimple/wiki
- https://udacity-br.slack.com/messages/C2C147PFE/convo/C2C147PFE-1510778957.000323/
- https://www.datasciencecentral.com/profiles/blogs/implemetation-of-17-classification-algorithms-in-r?utm_content=buffer20677&utm_medium=social&utm_source=facebook.com&utm_campaign=buffer
- http://dimplejs.org/advanced_examples_viewer.html?id=advanced_time_axis
- https://datavizcatalogue.com/index.html
- http://bl.ocks.org/enjalot/1525346
- https://www.kaggle.com/kernels
- https://github.com/PMSI-AlignAlytics/dimple/wiki/dimple.chart#noFormats
- https://github.com/PMSI-AlignAlytics/dimple/wiki/dimple.chart#defaultColors
- http://learnjsdata.com/read_data.html
- https://stackoverflow.com/questions/12064202/using-aggregate-to-apply-several-functions-on-several-variables-in-one-call
- http://www.jeromecukier.net/blog/2011/08/11/d3-scales-and-color/
- https://bl.ocks.org/Azgaar/b845ce22ea68090d43a4ecfb914f51bd
- http://dataremixed.com/2012/05/clarity-or-aesthetics-part-2-a-tale-of-four-quadrants/
- http://rawgit.com/
- http://htmlpreview.github.io/
- https://stackoverflow.com/questions/27336550/show-labels-inside-each-bubble-in-dimplejs-bubble-chart
- https://stackoverflow.com/questions/28653331/creating-a-legend-for-a-bubble-chart-using-d3
- https://bart6114.github.io/dimple/
- http://jsfiddle.net/acjwqpsL/2/
- http://jsfiddle.net/kgzo8Lsf/1/
- https://stackoverflow.com/questions/20688253/how-to-modify-the-size-and-color-of-a-pts-on-a-chart-depending-on-the-value-dim
- http://bl.ocks.org/tybyers/736da90eefe0c347a1d6
- http://jsbin.com/kovat/1/edit?html,js,output
- https://rawgit.com/ubirajaratheodoro/datavisualization-ProsperLoans/master/prosper.html
