# Como um cientista de dados compra um tênis de corrida?
[**Aplicação Web**](https://steam-rec.herokuapp.com/.) <br/>
[**Linkedin - Gustavo Bratfisch**](https://www.linkedin.com/in/gustavo-bratfisch/) <br/>
**Email** : gustavo@bratfisch.com.br <br/>

# Recomendação de Jogos na Steam

Antigamente a escolha na hora de comprar os jogos era muito mais dificil, por não ter tantas informções sobre o jogo e com qual ele mais era parecido, além do mais ter que comprar em lojas. Hoje em dia é muito mais simples, existem diversas plataformas com diferentes jogos para voce analisar e comprar, a quantidade de jogos cresceu rapidamente nos ultimos 10 anos e para saber jogos que seguem a mesma linha não é tão simples, nesse projeto vou utilizar um conjunto de dados com jogos da steam para criar um sistema de recomendação de jogo baseado em um jogo em particular (a escolha do leitor).

Com isso foi feito uma análise exploratorio dos dados mostrando um pouco mais sobre os dados e 
depois utilizaremos Flask para criar uma aplicação local para recomendação de jogos na steam (jogos com lançamento até maio de 2019) pelo site https://steam-rec.herokuapp.com/.

## Inicio

Podemos dividir esse trabalho em duas partes.

### - Primeira Parte: Visualização dos dados: **https://bit.ly/33rrK7A**

Nessa parte tentamos entender um pouco mais de como os dados estão distribuidos, fizemos alguns agrupamentos para ver quais são os generos majoritarios(grafico abaixo) e o tipo de jogo
![genre_game](https://user-images.githubusercontent.com/11478711/89574241-35100d00-d802-11ea-84d4-8226507566c1.png)

Criamos uma medida de avaliação baseada nas taxas de avaliações positivas e negativas dos jogos e fazendo um simples agrupamento conseguimos notar alguns pontos interessant e 
plotando conseguimos notar que jogos MM são que tem o maior feedback tanto positivo quanto negativo e nos restante seguem o mesmo padrão

![ratin_gem](https://user-images.githubusercontent.com/11478711/89574165-1447b780-d802-11ea-950b-6246a6c4b9a3.png)


### - Segunda Parte: Construção do Web Api **https://bit.ly/3iy1jmR**


Nessa segunda parte criamos nosso modelo utilziando a metodologia de recomendação baseada em conteúdo onde passamos descrições dos jogos, o modelo computa TF-IDF (Term Frequency-Inverse Document Frequency) que calcula uma matrix onde na coluna representa a uma avaliação da frequencia da palavra aparecer. Com essa matrix utilizamos uma metrica de similaridade (no nosso caso foi sigmoid_kernel) e por fim ordenamos pelo score feito anteriormente para ver os 8 jogos mais semelhantes.  A matrix final de similaridade é um arquivo muito grande, por isso foi feito do arquivo de TF-IDF utilizando o pacote pickle, e dentro da função do flask fazemos apenas a matrix da similaridade do nome do jogo que estamos buscando os jogos mais proximos.

Foi construido no Flask uma aplicativo muito simples para testar a sua funcionalidade e após foi feito o deploy pelo Heroku,

## Principais ferramentas utilizadas

* scikit-learn
* pandas
* numpy
* flask
* pickle
* heroku
* beautifulsoup4
* requests



