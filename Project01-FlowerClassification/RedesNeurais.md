# Redes Neurais Artificiais

As Redes Neurais Artificiais (RNAs) são um subconjunto dentro do grande conjunto de Machine Learning. As Redes Neurais conseguem ter um desempenho melhor para problemas mais complexos, se comparado com Árvore de Decisão, Support Vector Machine e outros. Elas são usadas em diferentes aplicações, tais como carros autônomos, tratamento de mídias (imagem, áudio e vídeo) etc.

## História

As Redes Neurais (RNs) foram conebidas em 1943 por **Warren McClulloch** (neurocientistaa) e **Walter Pitts** (matemático), quando descreveram no artigo [*A logical calculus of the ideas immanent in nervous activity*](https://www.cs.cmu.edu/~./epxing/Class/10715/reading/McCulloch.and.Pitts.pdf) o funcionamento dos neurônios por meio de modelagem matemática. 

O artigo descreve o funcionamento da atividade neural e demonstra que, a partir de suas características, é possível reproduzi-lo em uma estrutura lógica proposicional. Desse modo, Warren e Walter explicaram o comportamento de redes neurais humanas por meio de expressões lógicas.

Todo o estudo descrito por esses pesquisadores envolve discussões e suposições neurofisiológicas teóricas bem como a aplicação matemática. O artigo desencadeou muitos estudos focados na área e um maior desenvolvimento em arquiteturas neurais. 

## Funcionamento de um Neurônio

Um neurônio é composto por 4 partes: dentritos, corpo celular, axônio e terminais sinápticos.

- **Dentritos**: funcionam similar a uma porta, ou seja, é o local que receberá os sinais;
- **Corpo Celular**: processa os sinais recebidos pelos dentritos;
- **Axônio**: canal para transmitir os sinais;
- **Terminais Sinápticos**: permite a comunicação com outros neurônios.

<center><img src="../Imagens/neurônio.png"></center>

## Funcionamento de um Neurônio Artificial

- **Entrada de dados**: similar aos dentritos;
- **Processamento dos dados** similar ao corpo celular;
- **Saída dos dados**: similar aos terminais sinápticos.

## Perceptron

<center><img src="../Imagens/classificao-predicao.png" width="500"></center>

Considerando o modelo de classificação, **Frank Rosenblatt** resolveu este problema por meio do desenvolvimento de uma arquitetura computacional denominada **perceptron**, baseada no neurônio biológico, permitindo o aprendizado de máquina. Frank é considerando o pai do **Deep Learning.**

O **perceptron** é a unidade básica para a construção de uma rede neural. Ele é um modelo neural que associa pesos às entradas do modelo.

Um perceptron (ou neurônio artifical) é composto por 5 partes (camadas):

1. **Entradas**: os dados que serão processados;
1. **Pesos**: pesos associados às entradas;
1. **Bias**: é uma constate que vai adicionar um viés no cálculo do aprendizado do modelo. Importante para a construção da reta de separação;
1. **Soma**: vai executar a ponderação entre os dados e pesos;
1. **Ativação**: função de ativação que receberá os dados para gerar uma saída;
1. **Saída**: resultado final da classificação.

<center><img src="../Imagens/perceptron-partes.png" width="500"></center>

O aprendizado acontece nas funções de **Soma e Ativação**. Em conjunto, elas alteram os valores dos pesos e do bias, afim de traçar uma reta que consiga separar os elementos, possibilitando a classificação.

A função soma no perceptron tem muita ligação com a formação da reta de separação e que pode ser explicada matematicamente em um plano linear 2D.

O modelo matemático linear representa a função soma, que recebe N valores de entrada, se expressa da seguinte forma:

$$\Sigma = x_1 \times w_1 + x_2 \times w_2 + \ldots + x_n \times w_n$$

Representando esse modelo para que ele receba dois valores de entrada, teremos a seguinte equação:

$$\Sigma = x_1 \times w_1 + x_2 \times w_2$$

Ao igualar o sinal de soma à zero, pode-se isolar o valor de $x_2$ para obter uma equação da reta:

$$x_1 \times w_1 + x_2 \times w_2 = 0$$
$$x_2 \times w_2 = -x_1 \times w_1$$
$$x_2 = - \frac{x_1 \times w_1}{w_2}$$

Exemplo: $x_1 = 0, x_1 = 4, x_1 = 8$

Considerando $w_1$ e $w_2$ constantes na equação, temos então uma equação de primeira ordem centrada na origem, de modo que a alteração dos valores de $w_1$ e $w_2$ irão apenas rotacionar a reta, como mostrado no gráfico:

<center><img src="../Imagens/modeloineficaz.png" width="500"></center>

Para tirar a reta da origem, precisa-se adicionar um viés, ou bias, ao final da equação soma como uma constante:

$$\Sigma = x_1 \times w_1 + x_2 \times w_2 + b$$

Isolando novamente $w_2$, tem-se como resultado uma equação de 1° grau que poderá ser movida da origem.

$$x_1 \times w_1 + x_2 \times w_2 + b = 0$$
$$x_2 \times w_2 = -x_1 \times w_1 - b$$
$$x_2 = - \frac{x_1 \times w_1}{w_2} - \frac{b}{w_2}$$

Como resultado, ao otimizar os valores de pesos e bias, uma reta será capaz de dividir o plano de dados por suas classes.

<center><img src="../Imagens/modeloeficaz.png" width="500"></center>

Se considerarmos $x_2$ como $y$ e $x_1$ como $x$, pode-se encontrar a equação da reta:

$$y = -x \times \frac{w_1}{w_2} - \frac{b}{w_2}$$

Exemplo: $x_1 = 0, x_1 = 5, x_1 = 7$