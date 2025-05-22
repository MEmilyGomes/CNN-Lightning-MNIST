<div align="center">
  <img src="https://github.com/user-attachments/assets/ccb6f5f1-0e07-4eb2-aa7c-5f681c57a59c" alt="Descrição da imagem" width="1000"/>
</div>

<h1 align="center">Redes Neurais Convolucionais (CNN) 📸:</h1>

<h3 align="center">Classificando imagens do dataset MNIST com o módulo Lightning</h3>

<p align="center"><strong>Autores:</strong> Maria Emily Nayla Gomes da Silva e Yasmin Barbosa Shimizu</p>
<p align="center"><strong>Orientador:</strong> Prof. Dr. Daniel R. Cassar</p>

 <!-- 
<p align="center">
<img loading="lazy" src="http://img.shields.io/static/v1?label=STATUS&message=EM%20DESENVOLVIMENTO&color=GREEN&style=for-the-badge"/>
</p>
 -->

## 📝 Descrição
<p align="justify"> 
  Redes neurais convolucionais (CNN, do inglês <i>Convolutional Neural Networks</i>) são algoritmos de <i>deep learning</i> que reconhecem padrões específicos que caracterizam e distinguem classes em imagens. São compostas, seguindo a estrutura padrão de redes neurais artificiais, por uma camada de entrada, uma camada de saída, e camadas ocultas de processamento, diferenciando-se nas últimas, as quais são compostas pela combinação de camadas convolucionais e de <i>pooling</i>. [3] </p>

<p align="justify">
  As camadas convolucionais de uma CNN são caracterizadas por aplicar filtros na imagem, realçando regiões e traços característicos para a classificação. Já a camada de <i>pooling</i> reduz a dimensão da imagem, condensando as informações de vários pixel da região -- o <i>MaxPooling</i>, por exemplo, utiliza apenas o valor de maior píxel em blocos 2x2. Em geral, camadas convolucionais e de <i>pooling</i> são construídas em sequência, até que a matriz, após os processamentos anteriores, apresente apenas um ou poucos pixels que serão combinados e efetivamente associados a uma das classes. [3] </p>

<p align="justify">
  Este trabalho apresenta a construção de uma CNN utilizando dados do <i>dataset</i> <code>MNIST</code> importado do <code>PyTorch</code>, o qual contém inúmeros tensores de imagens em preto e branco, acompanhados de seus respectivos rótulos (<i>labels</i>) representando os dígitos. Partindo do código de referência feito por Nicola [1], foram realizadas modificações para torná-lo compatível com a biblioteca <code>Lightning</code>, permitindo a obtenção de um modelo otimizado para a identificação de números manuscritos. Para avaliar a qualidade do modelo, também foi gerada uma matriz de confusão.</p>
</p>

## 📔 Notebooks e arquivos do projeto
* `Imagens`: Pasta contento figuras utilizadas no README e o código para gerar a imagem de visualização do *dataset*.
  - `24Imagens_MNIST.png`: imagem de visualização do *dataset*.
  - `Construcao-Figura-24Imagens_MNIST.ipynb`: código para gerar a imagem de visualização do *dataset*.
  - `Matriz de Confusão - MNIST.png`: previsão obtida pela rede treinada.
  - `logos_ilum_cnpem_mcti_mec.jpg`: logotipos da institução na qual tal projeto foi realizado e seus vínculos.
* `CNN.ipynb`: caderno principal do projeto, com o *download* do *dataset* MNIST, além de construção, treinamento, teste e resultados obtidos com a CNN.
* `README.md`: descrição geral do projeto.
  
## 🗂️ MNIST - Dataset
<p align="justify">O dataset escolhido para desenvolver uma CNN com a biblioteca Lightning foi o MNIST. Esse conjunto de dados apresenta um extenso banco com 60.000 exemplos para treinamento, além de 10.000 exemplos previamente separados para teste. Dessa forma, trata-se de um conjunto vantajoso tanto para o treinamento quanto para a avaliação da performance do modelo treinado. A seguir, apresenta-se uma imagem com 24 exemplos disponíveis, cada um composto por um tensor da imagem e seu respectivo rótulo, que representa o número correspondente.</p>
<p> </p>
<div align="center">
  <img src="Imagens/24Imagens_MNIST.png" alt="Descrição da imagem" width="1000"/>
</div>

## 🏋️‍♀️ Construindo e Treinando a CNN

<p align="justify">
 Para a contrução da rede, foi usado como base o código desenvolvido por Nicola [1]. As alterações feitas estão relacionadas à biblioteca <code>Lightning</code>, que passou por atualizações nos últimos anos, deixando-a um pouco mais independente do <code>Pytorch</code>. Além disso, criamos os atributos <code>.y_true</code> e <code>.y_pred</code>, que salva as <i>labels</i> reais e previstas, respectivamente, para possibilitar o plot de uma matriz de confusão com os resultados. Também excluímos a função <code>main</code> para treinar e testar a rede manualmente, como feito em aula, e definimos a taxa de aprendizado fora da classe. Como o objetivo aqui é apenas testar a funcionalidade da rede construída, o treinamento foi feito em poucas épocas, com <code>NUM_EPOCAS = 5</code>. Por fim, todo o código foi comentado para melhor entendimento da estrutura da CNN.
</p>

  <!-- 
<p align="justify"> -> Biblioteca Lighting</p>
<p align="justify"> -> Cross Entropy</p>
 -->


## 🔢 Resultados Obtidos
<p align="justify">Os resultados obtidos foram excelentes. A baixa variabilidade dos dados, aliada ao grande número de exemplos e ao uso de uma ferramenta otimizada, a biblioteca Lightning, justifica a matriz de confusão apresentada a seguir, bem como a acurácia superior a 98% alcançada com apenas duas épocas. A concentração da densidade de predições na diagonal principal revela a qualidade do modelo, indicando que ele não está sobreajustado, mas sim realizando uma grande quantidade de previsões corretas.</p>
<p> </p>
<div align="center">
  <img src="Imagens/Matriz de Confusão - MNIST.png" alt="Descrição da imagem" width="500"/>
</div>


## 😁 Conclusão
<p align="justify">A biblioteca Lightning mostrou-se bastante eficiente para lidar com os dados disponíveis. Especificamente, trabalhamos com um grande volume de dados e com baixa variabilidade entre os exemplos. Ainda assim, apenas duas épocas de treinamento com três filtros foram suficientes para alcançar uma acurácia superior a 98%. Dessa forma, consideramos essa ferramenta bastante poderosa.</p>

## 🖇️ Informações técnicas
* Linguagem de programação: `Python 3.9`
* Software:  `Jupyter Notebook`
* Bibliotecas e Módulos: `Torch`, `Lightning`, `Typing`, `Scikit-learn`, `Seaborn`
<br>

## 👩‍🦳 Referências
$1.$ [**Nicola, Nicholas Di. “nicholas-dinicola/Lightning-Series"**](https://github.com/nicholas-dinicola/Lightning-Series)  
Acesso em 12 de abril de 2025. 

$2.$ [**GeeksforGeeks. “MNIST Dataset : Practical Applications Using Keras and PyTorch"**](https://www.geeksforgeeks.org/mnist-dataset/)  
Acesso em 12 de abril de 2025.

$3.$ **JAMES, Gareth; et al. An Introduction to Statistical Learning with Applications in Python.** 1. ed. Cham: Springer, 2023. p. 399–411.


## 🧠 Contribuições dos Colaboradores
| [<img loading="lazy" src="https://avatars.githubusercontent.com/u/172424897?v=4" width=115><br><sub> Maria Emily Nayla</sub>](https://github.com/MEmilyGomes)<br> [<sub>Ilum - CNPEM</sub>](https://ilum.cnpem.br/)<br> [<sub>Currículo Lattes</sub>](http://lattes.cnpq.br/9482558334105708)<br> | [<img loading="lazy" src="https://avatars.githubusercontent.com/u/171518829?v=4" width=115><br><sub>Yasmin Shimizu</sub>](https://github.com/yasminbshimizu)<br> [<sub>Ilum - CNPEM</sub>](https://ilum.cnpem.br/)<br> [<sub>Currículo Lattes</sub>](https://github.com/yasminbshimizu)<br> [<sub>Linkedin</sub>](https://www.linkedin.com/in/yasminbshimizu/) | [<img loading="lazy" src="https://github.com/user-attachments/assets/463d4753-7fa4-4a42-aa54-409e4150bb51" width=115><br> <sub> Prof. Dr. Daniel R. Cassar </sub>](https://github.com/drcassar)<br> [<sub>Ilum - CNPEM</sub>](https://ilum.cnpem.br/)<br> [<sub>Currículo Lattes</sub>](http://lattes.cnpq.br/1717397276752482) | 
| :---: | :---: | :---: | 

#### Para o Projeto:
* Emily Gomes: Atualizações na construção, treinamento e análise da previsão de uma CNN utilizando o Lightning.
* Yasmin Shimizu: Atualizações na construção, treinamento e análise da previsão de uma CNN utilizando o Lightning.

#### Para o Repositório GitHub:
* Emily Gomes: README e upload do notebook Jupyter referente a construção, treinamento e previsão da CNN.
* Yasmin Shimizu: README, upload de imagens e upload do notebook Jupyter referente à figura "24Imagens_MNIST.png".


**Orientação e Revisão:** Prof. Dr. Daniel R. Cassar.
