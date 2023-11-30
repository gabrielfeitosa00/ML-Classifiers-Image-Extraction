# Extração de Características usando Hu Moments

## Grupo
 Gabriel Perino Feitosa RA:2101360

 Gabriel Sarubo de Andrade Lemes Sousa RA: 1997432

Vinicius Lara RA: 2211254

## Dependências
O Código fonte do repositório se encontra no [link](https://github.com/gabrielfeitosa00/ML-Classifiers-Image-Extraction).


Para execusão do projeto são necessárias as seguintes bibliotecas:

* cv2
* bar
* sklearn
* numpy

O dataset utilizado no projeto se encontran o [link](https://www.kaggle.com/datasets/tarandeep97/covid19-normal-posteroanteriorpa-xrays).

Para que o projeto funcione corretamente estruture as pastas de de imgens da seguinte maneira:

```
.
└── root/
    ├── images_full/
    │   ├── covid/
    │   └── normal/
    └── images_split/
        ├── covid/
        └── normal/
```

## Descritores
O trabalho refatorou a estrutura do descritor de histograma e implementou o Hu moments, um tipo de descritor baseado nas formas dos objetos contidos da imagem.

Os momentos de uma imagem podem ser definidos como uma média ponderada das intensidades dos pixels de uma imagem podendo ser represnetadas pela fórmula:

![Alt text](https://learnopencv.com/wp-content/ql-cache/quicklatex.com-57be077fade2b4294b4eb912ac93aa16_l3.png)

Onde i e j são números inteiros e I(x,y) representa a intensidade de um determinado pixel. Além dos momentos de uma imagem existem os momentos centrais que apenas subtraem o centróide de x e y da fórmula:


![Alt text](https://learnopencv.com/wp-content/ql-cache/quicklatex.com-e5a36c413410b5751103411993ce127a_l3.png)

Os momentos centrais de uma imagem são independentes de translação, no entanto ainda são dependetes de escala e rotação. Para isso são calculados os Hu moments uma série de 7 momentos que são baseados nos momentos centrais de uma imagem, os 6 primeiros momentos são independentes  de translação,escalaa e rotação e o último permite a distinção entre imagens espelhadas com a mesma forma. Destes 7 valores podem ser extraídos um vetor de características da imagem.


## Classificadores

Como o trabalho fez uso do projeto da classificação como base ele utilizou os mesmos classificadores sendo eles Random Forest, Support Vector Machine e uma Rede Neural do tipo Perceptron.

Depois de rodar cada um dos clássficadores os resultados obtidos de acurácia foram os seguintes:

* Random Forest: 89.29%

* Support Vector Machine: 85.71%

* Rede Neural: 80.36%