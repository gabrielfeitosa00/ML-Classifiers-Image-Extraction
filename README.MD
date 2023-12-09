# Extração de Características usando Hu Moments

## Grupo

- Gabriel Perino Feitosa RA:2101360
- Gabriel Sarubo de Andrade Lemes Sousa RA: 1997432
- Vinicius Lara RA: 2211254

## Dependências
O Código fonte do repositório se encontra [neste repositório do GitHub](https://github.com/gabrielfeitosa00/ML-Classifiers-Image-Extraction).

Para a execução do projeto, é necessário instalar as seguintes bibliotecas:

* opencv-python
* progress
* scikit-learn
* numpy

O dataset utilizado no projeto se encontra [neste link no Kaggle](https://www.kaggle.com/datasets/tarandeep97/covid19-normal-posteroanteriorpa-xrays).

Para que o projeto funcione corretamente, estruture as pastas das imagens da seguinte maneira:

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
O trabalho refatorou a estrutura do descritor de histograma e implementou o Hu moments, um tipo de descritor baseado nas formas dos objetos contidos na imagem.

Os momentos de uma imagem podem ser definidos como uma média ponderada das intensidades dos pixels da imagem e pode ser representada pela fórmula abaixo:

![Alt text](https://learnopencv.com/wp-content/ql-cache/quicklatex.com-57be077fade2b4294b4eb912ac93aa16_l3.png)

Onde i e j são números inteiros e I(x,y) representa a intensidade de um determinado pixel. Além dos momentos de uma imagem existem os momentos centrais que apenas subtraem o centróide de x e y da fórmula:

![Alt text](https://learnopencv.com/wp-content/ql-cache/quicklatex.com-e5a36c413410b5751103411993ce127a_l3.png)

Os momentos centrais de uma imagem são independentes de translação, no entanto ainda são dependentes de escala e rotação. Para isso são calculados os Hu moments, que são uma série de 7 momentos baseados nos momentos centrais de uma imagem, os 6 primeiros momentos são independentes da translação, escala e rotação e o último permite a distinção entre imagens espelhadas com a mesma forma. Destes 7 valores podem ser extraídos um vetor de características da imagem.

## Classificadores

Como o trabalho fez uso do projeto de classificação como base, ele utilizou os mesmos classificadores, sendo eles: Random Forest, Support Vector Machine e uma Rede Neural do tipo Perceptron.

Depois de executar cada um dos classficadores, os resultados de acurácia obtidos foram os seguintes:

* Random Forest: 89.29%
* Support Vector Machine: 85.71%
* Rede Neural: 80.36%

## Apresentação

[Link onde pode ser encontrado a apresentação do trabalho:](https://drive.google.com/file/d/1Im_f3oMrDMbTm4HmBPH0SI6m9Ctyr5WG/view?usp=sharing)
