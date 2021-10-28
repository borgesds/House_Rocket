# Vendas da Loja Rossmann

<p align="center">
  <img width="1000" height="220" src="https://camo.githubusercontent.com/f1d71e6ee558367c9910a433915be7e226aebd0f9a8efa64e9151304e437bb1d/68747470733a2f2f7777772e726f73736d616e6e2e64652f64616d2f6a63723a30643062623036612d383532372d346437632d616337302d3763623630653764303030372f524f53534d414e4e5f576f72745f42696c645f436c61696d5f53636875747a5f4c5f636d796b2e323031382d30392d32312d30392d35382d32382e6a7067"/>
</p>

**Aviso:** O seguintes dados foram retirado do site https://www.kaggle.com/c/rossmann-store-sales/overview, a empresa existe e os resultados apresentados nesse projeto não tem vínculo com os resultados reais da empresa, o contexto, o CFO, e as questões de negócios existem apenas para elaboração desse contexto.


# Questão de negócio

Rossmann opera mais de 3.000 drogarias em 7 países europeus. Atualmente, os gerentes de loja da Rossmann têm a tarefa de prever suas vendas diárias com até seis semanas de antecedência. As vendas da loja são influenciadas por muitos fatores, incluindo promoções, competição, feriados escolares e estaduais, sazonalidade e localidade. Com milhares de gerentes individuais prevendo vendas com base em suas circunstâncias únicas, a precisão dos resultados pode ser bastante variada.

# Problema de Negócio

A requisição para prever as vendas diárias nas seis semanas das lojas vem diretamente do CFO, que quer prever o budget das lojas durante esse tempo. O mesmo quer fazer uma reforma das lojas e para saber um valor que possa investir nessas reformas deve se encaixar nos valores de vendas futuras.

# Planejamento da Solução

Para um planejamento adequado foi usado o método CRISP:

<p align="center">
  <img width="1000" height="500" src="https://www.researchgate.net/profile/Francisca-Oladipo/publication/341205300/figure/fig1/AS:888511267893249@1588849002362/Ten-Steps-of-the-Cross-Industry-Process-for-Data-Mining-source.jpg"/>
</p>

- Questão de negócio;
- Entendimento do negócio;
- Coleta dos dados;
- Limpeza dos dados;
- Exploração dos dados;
- Modelagem dos dados;
- Algoritimos de machine learning;
- Avaliação dos algoritmos;
- Aqui pode ser implementado um novo ciclo para melhorar o modelo e os algoritimos, ou finalizar e colocar o modelo em produção.
**Obs:** É sempre bom colocar o modelo em procução no fim do primeiro ciclo para receber feedback do time de negócio e assim melhorar os algoritomos na proxima rodada.

## Como será o caminho para a solução?

Com a coleta dos dados o primeiro passo é a limpeza desses dados. Visualizar como está os dados e criar um dataset único criando variáveis a partir das variáveis padrão.Com essas novas variáveis temos condições de implementar feature engineering que é o processo de usar o conhecimento de domínio para extrair recursos de dados brutos. Um recurso é uma propriedade compartilhada por unidades independentes nas quais a análise ou previsão deve ser feita. Para te uma base se cria hipóteses que levantam questões para análise exploratoria dos dados, que tinha objetivo de entender o negócio do ponto de vista dos dados e o sentimento de quais variáveis seria mais importante para o modelo.
Essas variáveis importantes que dita o passo para feacture selection que abre o caminho para rodar o Boruta, que é um método de seleção de recursos totalmente relevante. Ele tenta capturar todos os recursos importantes e interessantes que você possa ter em seu conjunto de dados com relação a uma variável de resultado.
Depois dessa modelagem é onde entra o MACHINE LEARNING, implementamos 5 algoritmos onde um é um baseline, 2 lineares e 2 não lineares para medir a complexidade dos dados. Implementamos o cross validation para fazer a medição real da performance de cada um.
E por fim avaliação do modelo ou algoritmo para ver quanto isso impacta no negócio a partir dos resultados pelo modelo (MAE, MAPE, RMSE)


## Resultado 

O nosso modelo aprensentou resultados importantes e visualizando sua predição vemos os valores que cada loja vai faturar nas proximas 6 semanas. Na coluna MAE mostra a variação dos resultados dentro dessa predição que pode ser descrita em porcentagens pela coluna MAPE, para uma visualização descritiva observe a tabela de amostras:

- Tabela Amostras

| store | predictions | worst_scenarios | best_scenarios | MAE | MAPE |
| ----- | ----------- | --------------- | -------------- | --- | ---- |
|  667 |  312517.218750 |  312010.863017 |  313023.574483 |  506.355733 | 0.057548|
|  113 | 223261.093750 |  222748.297997 |  223773.889503 |  512.795753 | 0.092686 |
|  1037 |  236532.109375 |  235925.201700 |  237139.017050 |  606.907675 | 0.102723 |
|  537 |  221320.406250 |  220792.616924 |  221848.195576 |  527.789326 | 0.079885 |
|  383 |  612645.500000 |  611608.362041 |  613682.637959 |  1037.137959 | 0.062283 |
|  292 |  105020.351562 |  101651.673044 |  108389.030081 |  3368.678518 | 0.568189 |

A maioria das lojas estão concentradas em uma região do MAPE entre 0.05 e 0.15, e existem lojas com porcentagens altas, e podem ser vista no grafico 01. O CFO vai analisar se essas lojas com um MAPE muito alto vão entrar nessas reformas ou não.

- Gráfico 01 (Lojas em relação ao MAPE)

![graf1](https://user-images.githubusercontent.com/82332461/138337442-775efa82-15b1-4144-9e15-0820df7b942d.png)


Totais:
O resultado para as próximas 6 semanas é entorno de R$ 283.651.392,00 para todas as lojas juntas.
O resultado do pior cenário para as próximas 6 semanas é entorno de R$ 282.925.070,57 para todas as lojas juntas.
O resultado do melhor cenário para as próximas 6 semanas é entorno de R$ 284.377.741,83 para todas as lojas juntas.

- Tabela Totais

| Scenarios  |  Values |
| ------------------- | ------------------- |
|  predictions |  R$ 283,651,392.00 |
|  worst_scenarios |  R$ 282,925,070.57 |
|  best_scenarios |  R$ 284,377,741.83 |

- Gráfico 02 (Machine Learning Performance)

O primeiro gráfico mostra as predições nas próximas 6,a linha laranha é a predições e a azul são as vendas reais, as sombras são as variância entre lojas. O segundo gráfico o error rate que é a divisão da coluna preditions por sales e é representada em porcentagem. Em um modelo perfeito o resultado estaria perto do 1, mãs o modelo não é perfeito, então acima da linha do 1 quer dizer que o modelo fez uma previsão de superestimação, e abaixo uma subestimação ao longo do tempo.
O terceiro grafico mostra a distribuição dos erros que o modelo gerou procimo de uma distribução normal. O quarto gráfico junto com o terceiro é muito usado para análise de resíduo, e o ultimo gráfico mostra as predições em relação ao error o que quanto maior os valores das da predições maiores são os erros.

![graf](https://user-images.githubusercontent.com/82332461/138327224-945e646b-181f-4ea8-9f28-1fc7eff0c06c.png)


#  Storytelling

https://user-images.githubusercontent.com/82332461/138787724-ea24660d-ff7f-4134-bf41-39cc64427ff3.mp4

#  Próximos Passos
As lojas que tem o MAPE muito alto podem ser criado modelos específicos para elas, como colocar variáveis. O CFO pode determinar uma melhor predição dessas lojas e assim voltando para o CRISP ou podendo descartar essas lojas.

#  Conclusão
Foi um desafio muito grande em fazer esse projeto, machine learning não é simples tem que ter muito estudo. Ciência de dados é desafio, é compreenção, aprendizado, e acima de tudo visão do negócio onde te apresenta a direção correta para aplicar os métodos para análises dos dados.

 





