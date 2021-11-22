# HOUSE ROCKET

<p align="center">
  <img width="1000" height="380" src="https://static.seattletimes.com/wp-content/uploads/2020/04/04242020_forsalesignWA_000009-1560x917.jpg"/>
</p>


**Aviso:** O seguintes dados foram retirado do site https://www.kaggle.com/harlfoxem/housesalesprediction, a empresa existe e os resultados apresentados nesse projeto não tem vínculo com os resultados reais da empresa, o contexto, o CEO, e as questões de negócios existem apenas para elaboração desse contexto.

# Sobre

A House Rocket é uma plataforma digital que tem como modelo de negócio, a compra e a venda de imóveis usando tecnologia. Sua principal estratégia é comprar boas casas em ótimas localizações com preços baixos e depois revendê-las posteriormente à preços mais altos. Quanto maior a diferença entre a compra e a venda, maior o lucro da empresa e portanto maior sua receita.

Entretanto, as casas possuem muitos atributos que as tornam mais ou menos atrativas aos compradores e vendedores e a localização e o período do ano também podem influenciar os preços.

# Questão de negócio

A principal estratégia é comprar boas casas em ótimas localizações com preços baixos e depois revendê-las posteriormente à preços mais altos. Quanto maior a diferença entre a compra e a venda, maior o lucro da empresa e portanto maior sua receita.


# Problema de Negócio

O CEO da empresa fez uma reunião e colocou alguns pontos para que as casas fossem compradas:

As casas possuem muitos atributos que as tornam mais ou menos atrativas aos compradores e vendedores e a localização e o período do ano também podem influenciar os preços.

**Perguntas:**

1- Quais casas o CEO da House Rocket deveria comprar e por qual preço de compra?


2- A House Rocket deveria fazer uma reforma para aumentar o preço da venda? Quais seriam as sugestões de mudanças? Qual o incremento no preço dado por cada opção de reforma?


# Planejamento da Solução

Com a primeira análise dos dados, verificamos o mínimo, maximo, média, mediana e outras variáveis para ter um ponto de partida:


![521](https://user-images.githubusercontent.com/82332461/141848094-8e7bcc77-3e19-49c8-9000-7e30ae8d2526.png)

Com esses dados em mãos, foi discutido com o CEO alguns pontos de interesse. O nosso imóvel mais barato é $75 mil dólares e o mais caro é $7.700 milhões de dólares, a média de preço dos imóveis é de $540 mil dólares e a mediana é $450 mil dólares.
A conclusão do CEO foi em estimar as compra abaixo da mediana e verificar as melhores casas com vista para a água que tiverem abaixo de $800 mil dólares.

# Criação de hipóteses e visualização de correlação.

## Hipóteses e resultados:


- H1: A maioria das casas com 3 quartos são acima da mediana do preço.
    - **FALSA**  A maioria das casa com 3 quartos são abaixo da mediana do preço.
    
 
- H2: A maioria das casas com 3 quartos e 2 banheiros são acima da mediana do preço.
    - **FALSA** A maioria das casa com 3 quartos e 2 banheiro são abaixo da mediana do preço.
    

- H3: A maioria das casas que tem 3 quartos e 2 banheiros são abaixo da mediana de m² construídos .
    - **VERDADEIRO** A maioria das casas que tem 3 quartos e 2 banheiros são abaixo da mediana de m² construídos.
    
 
- H4: Casas com com vista para água são 100% mais caras que a mediana do preço.
    - **VERDADEIRO** A maioria das casas são 100% ou acima que a mediana do preço.
 

- H5: A maioria das casas com porão e 2 andares são mais caras que que a mediana do preço.
    - **VERDADEIRO** A maioria das casas são mais caras que a mediana do preço.


- H6: Casas com a data de construção igual ou menor que 1955 são mais barato que a mediana do preço.
    - **VERDADE** Existe mais casa igual ou menor que 1955 que são acima da mediana, entretanto pode ser considerado um empate de quantidade de unidades que estão muito proximas na somatória.


- H7: A maioria das casas com datas acima de 1990 que tiveram reformas são mais caras que a mediana.
    - **VERDADE** A maioria das casas são mais caras que a mediana.


- H8: A maioria das casas com 2 andares e 2 banheiros são mais caras que a mediana do preço.
    - **VERDADE** A maioria das casas são mais caras que a mediana.

- H9: A maioria das casas com m² de contrução e m² de lote abaixo da mediana são mais baratas que a mediana do preço.
    - **VERDADE** A maioria das casas com m² de construção e de lote abaixo da mediana são mais baratas que a mediana.


- H10: A maioria das casas acima do ano 2000 de construção são mais caras que a mediana do preço.
    - **VERDADE** A maioria das casas são mais caras que a mediana.


***CONLUSÃO E RELEVÂNCIA:***

|Hipoteses  |  Conclusão  |  Relevancia|
|----------- | ----------- | ------------|
|H1          | Falsa       | Baixa |
|H2          | Falsa       | Alta |
|H3          | Verdadeira  | Alta |
|H4          | Verdadeira  | Alta |
|H5          | Verdadeira  | Baixa |
|H6          | Verdadeira  | Baixa |
|H7          | Verdadeira  | Media |
|H8          | Verdadeira  | Media |
|H9          | Verdadeira  | Alta |
|H10         | Verdadeira  | Media |


## Correlação:

- Gráfrico 01 (Atributos Numéricos)

![corrnumerical](https://user-images.githubusercontent.com/82332461/142925081-c066505d-44aa-44fa-88be-b78e75a9954b.png)


- Gráfrico 02 (Atributos Categóricos)

![corratrcate](https://user-images.githubusercontent.com/82332461/142925434-d40ccadc-3a8d-4886-bb48-5213ac4090e3.png)


# Resultados 

***Respondendo as perguntas do CEO:***


1- Quais casas a House Rocket deveria comprar e por qual preço de compra?

    - As casas que a House Rocket deveria comprar devem está abaixo da mediana. As casa com vista para a água deve ser avaliadas individualmente.
    - São 10864 casas que tem o preço abaixo da mediana.
   

2- A House Rocket deveria fazer uma reforma para aumentar o preço da venda?

    - As casa com condições bad deveriam passar por uma reforma, já as regulares deveriam ser verificadas caso a caso. As casas com vista para a água deveria passar por uma reforma para ser mais atrativas.
    
       
       - São 706 casas que tem o preço abaixo da mediana que estejam na condição good.
       - São 10158 casas que tem o preço abaixo da mediana que estejam na condição bad ou regular.
          - São 166 casas que tem o preço abaixo da mediana que estejam na condição bad que precisam de uma reforma.
          - São 9992 casas que tem o preço abaixo da mediana que estejam na condição regular que precisam ser avaliadas caso a caso.
          
       - São 8 casas que estejam na condição regular abaixo da mediana com vista para a água que devem ter reformas.
       
       - Quantidade de casas com vista para a água que não são 100% mais caras que a mediana do preço: 38 unidades
              - bad =      1
              - good =     2
              - regular =  35
        




3- Qual o incremento no preço dado por cada opção de reforma?

    - Casas com condições bad devem ter um custo de até 20% no valor na reforma.
    - Casas com condições regular devem ter um custo de até 12% no valor na reforma.
    - As casas podem ter um acrécimo ou diminuição nessa porcentagem de acordo com o grau de qualidade do imóvel.


***Mapa:***

- Mapa das casas para comprar (O mapa estará no relatorio do Power BI para ser melhor visualizado)

 ![newplot](https://user-images.githubusercontent.com/82332461/142927357-4f7ecdf8-f8ce-4e3d-b5f6-d0e6766f10f0.png)


![newplot1](https://user-images.githubusercontent.com/82332461/142927373-ca7757c3-4b8d-43a9-af23-3e4ea970dcd4.png)

 
 
 ## Resultado dos custos
 
**1 - Preço total de investimento para a compra:**

 - O total das somas dos preços das casas para compra é $3490407741.0.
 
 
**2 - Soma das casas pela condição e total da soma do custo da reforma:** 
- Somatoria dos preços das casa com codições bad $42257311.0, e somatoria custo para reformar $8451462.2.

- Somatoriados preços das casa com codições good $225036167.0, e somatoria custo para reformar $0.0.

- Somatoriados preços das casa com codições regular $3223114263.0, e somatoria custo para reformar $386773711.56.

 

**3 - Resultado de venda:** 

*Casas com condições bad vai ter 10% adcionado ao final para a venda.*

*Casas com condições regular vai ter 15% adcionado ao final para a venda.*

*Casas com condições good vai ter 20% adcionado ao final para a venda.*
 
- O lucro da vendas das 10902 casas é de $591561306.9.


 





