# Utilização de IA na construção de ferramentas interativas para Websites. 

#### Alun(o/a): Giovanna Santoloni Dohnert giovannasantoloni (github.com)
#### Orientador(/a/es/as): Manoela Kohler

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- Nome do arquivo: Projeto Final Curso BI Master 2021.1_Giovanna Dohnert


### Resumo
O projeto apresentado tem por objetivo desenvolver uma ferramenta interativa para o Website de uma rede de Pet Shop, que permita que a empresa se conecte com seus clientes gateiros – O nicho que impulsiona mais vendas para a empresa. Buscando gerar maior interação desses clientes e aumentar a visibilidade do site, criou-se um modelo de classificação com o objetivo de identificar e classificar dados de imagens enviadas pelos donos dos pets. Para a construção do modelo, foram consideradas as 10 raças mais populares entre os felinos na região de atuação do Pet Shop. 

Visando reduzir o tempo de treinamento do modelo e melhorar sua precisão, adotamos o Transfer Learning utilizando pesos pré-treinados da arquitetura ResNet50V2.

### Abstract 

The project presented aims to develop an interactive tool for the website of a Pet Shop chain, which allows the company to connect with cat owners customers – the clientele that drives more sales for the company. Seeking to generate interaction between these customers and the website, an image classification model was created to identify and classify data from images sent by clients. For the construction of the model, the 10 most popular feline breeds in the region where the Pet Shop operates were considered.

To reduce the model training time and improve its accuracy, we adopted Transfer Learning using pre-trained weights from the ResNet50V2 model.

### 1. Introdução

O código apresentado é uma modelagem em Python criada para treinar uma rede neural convolucional para classificação de imagens, utilizando a arquitetura ResNet50V2 pré-treinada para classificar imagens do dataset em dez categorias.

### 2. Modelagem

A base de dados foi definida através do caminho do diretório contendo as imagens, e estabelecemos parâmetros importantes no início do cógido, como o número de classes, o tamanho das imagens (224x224) e o tamanho do lote para treinamento. Em seguida, foram criadas listas para armazenar os nomes das classes e o número de arquivos por classe. Utilizando esses dados, geramos um gráfico de barras para vislumbrar o número de arquivos por classe e conferir o balanceamento dos dados. 

Aplicamos um gerador de imagens para a definição dos conjuntos de dados de treinamento, validação e teste, carregando os dados do dataset. Os pesos da arquitetura ResNet50V2 pré-treinada foram carregados, e suas camadas da base são congeladas, para que não sejam treinadas novamente. Para reduzir o overfitting, utilizamos recursos como ‘Global Average Pooling’ e a adição de uma camada de dropout de 0,5, indicando que metade dos neurônios da camada anterior foram aleatoriamente desativados durante o treinamento. Configuramos o otimizador Adam com uma taxa de aprendizado fixa ao modelo. 

Através da função ‘ModelCheckpoint’,  criamos o caminho para salvar apenas o melhor modelo gerado durante o treinamento. Em seguida, o modelo é treinado durante 50 épocas, com um tamanho de lote especificado nos parâmetros (32). No treinamento, o modelo se auto-ajusta para minimizar a perda (loss) e melhorar a precisão (acc) nas tarefas de classificação. 

### 3. Resultados

Após o treinamento, calculamos as métricas de F1 Score e Accuracy Score. O modelo obteve uma acurácia de 91.62% no conjunto de teste, o que indica que ele foi capaz de classificar corretamente a maioria das amostras nesse conjunto. O F1 Score também se mostrou alto, alcançando o valor de 91.59%, e indicando equilíbrio entre a capacidade do modelo de identificar corretamente as amostras. Geramos a matriz de confusão com a finalidade de obter uma visão detalhada do desempenho do modelo, mostrando como as amostras foram classificadas por classe. 
	
### 4. Conclusões

Analisando o processo de treinamento, verificamos uma tendência de redução da perda e aumento da precisão, tanto no conjunto de treinamento quanto no conjunto de validação. Isso confirma que o modelo está aprendendo e se ajustando aos dados ao longo das épocas. A matriz de confusão e os gráficos gerados ao final do trabalho, confirmam tal progresso de desempenho ao longo do treinamento.

Os resultados apresentados mostram que o modelo foi capaz de aprender os padrões relevantes sobre os dados e realizar previsões precisas, atingindo uma acurácia de 91.62% no conjunto de teste, um F1 Score de 91.59%. 

Matrícula: 211.100.017

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*

