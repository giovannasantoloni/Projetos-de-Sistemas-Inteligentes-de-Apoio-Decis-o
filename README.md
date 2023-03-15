# Utilização de IA na construção de ferramentas interativas para Websites. 

#### Alun(o/a): Giovanna Santoloni Dohnert giovannasantoloni (github.com)
#### Orientador(/a/es/as): Manoela Kohler

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- Nome do arquivo: Projeto_Final_Curso_BI_Master_2021_1_Giovanna_Dohnert.ipynb

---

### Resumo
	O projeto apresentado tem por objetivo desenvolver uma ferramenta interativa para o Website de uma rede de Pet Shop, que permita que a empresa se conecte com seus clientes gateiros – O nicho que impulsiona mais vendas para a empresa. Buscando gerar interação desses clientes com o site, e aumentar a visibilidade dos anúncios de produtos e promoções. 
	Gateiros sempre gostam de saber mais sobre seus filhos felinos. A maior parte dos donos de gatos adotaram seus pets em campanhas de adoção anuais promovidas pela rede Pet Shop. No entanto, raramente os gatinhos adotados vem com identificação da raça, origem, porte, entre outras curiosidades sobre o animal. Por isso, pensando em prover maiores informações aos seus donos, criou-se um modelo de classificação de imagem para identificar e classificar dados de imagens enviadas por clientes gateiros. Para a construção do modelo, foram consideradas as 10 raças mais populares de felinos da cidade de atuação do Pet Shop. 
	Visando reduzir o tempo de treinamento do modelo e melhorar sua precisão, adotamos o Transfer Learning utilizando pesos pré-treinados do modelo VGG16.

### Abstract 
	The project presented aims to develop an interactive tool for the website of a Pet Shop chain, which allows the company to connect with cat owners customers – the clientele that drives more sales for the company. Seeking to generate interaction between these customers and the site, and increase the visibility of product ads and promotions.
	Cat owners always like to know more about their feline. Most cat owners adopted their pets in annual adoption campaigns promoted by the Pet Shop. However, rarely do adopted kittens come with breed identification, origin, size, among other curiosities about the animal. Therefore, thinking of providing more information to their owners, an image classification model was created to identify and classify data from images sent by clients. For the construction of the model, the 10 most popular feline breeds in the city where the Pet Shop operates were considered.
	To reduce the model training time and improve its accuracy, we adopted Transfer Learning using pre-trained weights from the VGG16 model.
---
---
###1. Introdução
---
O código apresentado é uma modelagem de rede neural convolucional para classificação de imagens, com base em um conjunto de dados de 10 classes. A arquitetura utilizada foi a VGG16 pré-treinada, com camadas adicionais incluídas para adaptá-la ao problema em questão. Além disso, foram realizadas transformações nas imagens de treinamento para aumentar a sua variabilidade. O modelo foi compilado com a função de perda 'categorical_crossentropy' e otimizador RMSprop, e treinado com 50 épocas. Por fim, foi avaliado utilizando um conjunto de teste e gerando uma matriz de confusão para avaliar a sua performance.

###2. Modelagem
---
Foi feita uma modelagem em Python para treinar uma rede neural convolucional utilizando a arquitetura VGG16 pré-treinada para classificar imagens em dez categorias. A base de dados é definida através do caminho do diretório contendo as imagens e o tamanho das imagens é configurado como 225x225 pixels. Além disso, um gerador de imagens é criado utilizando a biblioteca Keras para aplicar transformações nas imagens de treino, como rotação, deslocamento horizontal e vertical, zoom, espelhamento horizontal e vertical, brilho, cisalhamento, alteração do canal de cores, entre outras.
O dataset é separado em três conjuntos: treinamento, validação e teste. O conjunto de treinamento e validação são gerados a partir do gerador de imagens criado anteriormente, enquanto o conjunto de teste é gerado utilizando outro gerador que apenas realiza a normalização das imagens.
A arquitetura VGG16 pré-treinada é carregada e camadas adicionais são acrescentadas ao final da rede, incluindo uma camada densa com ativação ReLU e uma camada de dropout para evitar overfitting. A função de ativação da camada de saída é softmax, pois se trata de um problema de classificação multiclasse.
As camadas da base da VGG16 são congeladas, o que significa que elas não serão atualizadas durante o treinamento das camadas adicionais. O modelo é compilado utilizando o otimizador RMSprop, a função de perda categorical_crossentropy e a métrica de acurácia.
O modelo é treinado por 50 épocas, utilizando o conjunto de treinamento e validação. A cada cinco épocas, é aplicado um learning rate scheduler para reduzir a taxa de aprendizado pela metade. Por fim, o modelo é avaliado utilizando o conjunto de teste e a matriz de confusão é gerada para verificar o desempenho do modelo na classificação das imagens.
Na construção do modelo de classificação de imagens proposto, foi aplicado Transfer Learning, fazendo uso dos pesos pré-treinados do modelo VGG16 com a finalidade de melhorar a precisão do modelo, e reduzir o tempo e o custo de treinamento.

###3. Resultados
---
Com base nos resultados apresentados, é possível observar que o modelo utilizado apresentou uma acurácia média baixa de aproximadamente 25%. As acurácias de validação também não demonstraram melhorias significativas ao longo das épocas, variando em torno de 20% a 28%. Isso indica que o modelo pode não estar conseguindo capturar bem as características das imagens de treinamento, levando a uma baixa capacidade de generalização e, consequentemente, a baixas acurácias nas imagens de validação.

###4. Conclusões
---
Os resultados mostram as perdas (loss) e as acurácias (acc) do conjunto de treinamento e do conjunto de validação a cada época. Além disso, também mostra a taxa de aprendizagem (lr) utilizada em cada época. Os resultados indicam que, apesar de a acurácia do conjunto de validação ter melhorado gradualmente ao longo do tempo, permaneceu em um nível relativamente baixo (inferior a 30%). Além disso, a perda do conjunto de validação também permaneceu relativamente alta. Esses resultados sugerem que o modelo pode estar sofrendo de overfitting, onde ele se torna muito ajustado aos dados de treinamento e não generaliza bem para dados novos.

Matrícula: 211.100.017

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
