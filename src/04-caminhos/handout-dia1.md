---
title: Caminhos em Labirinto - Heurística
subtitle: Técnicas de Programação
author: Igor Montagner
...


Nesse handout iremos formalizar duas grandes ideias:

- a representação do nosso labirinto
- como representar o algoritmo senso comum de sair do labirinto seguindo as paredes

## O Labirinto

Um primeiro passo para definirmos nossos algoritmos é definir como o labirinto será representado para nosso código. Inicialmente, o labirinto sempre é recebido como uma `String` com o seguinte formato:

```
#####
#...#
###.#
```

- cada linha contém somente caracteres `'.'` (livre) ou `'#'` (parede)
- todas as linhas contém o mesmo número de caracteres

O primeiro passo será transformar essa `String` em um array `boolean casas_ocupadas[][]` em que a posição `casas[i][j]` contém `true` se a casa é parede e `false` caso contrário. Isso será feito no exercício de implementação do PrairieLearn. 

## Algoritmo de Seguir Paredes

Ao longo das próximas aulas iremos criar várias versões do algoritmo `ENCONTRA_SAIDA(L, I, J, CAMINHO)` onde

- `L` é um labirinto representado como `boolean[][]`
- `I, J` é a posição inicial
- `CAMINHO` é um array que será preenchido com as posições do labirinto até a saída

A primeira ideia que estudaremos para a criação de um algoritmo é simples:

> Para sair do labirinto basta colocar a mão direita na parede mais próxima e seguir sempre com essa mão na parede. Eventualmente chegamos na saída.

**Exercício**: isso chega na saída? Como você argumentaria que isso é verdade?

[line-spacer]

[line-spacer]

Para implementar esse algoritmo precisamos definir algumas coisas:

- estado: quais variáveis representam o andamento do algoritmo. 
- critério de parada: quando decidimos que chegamos no fim? 

Uma boa maneira de entender esses pontos é simular a ideia em alguns cenários simples. Em todos labirintos, a posição atual está marcada com `o`. Pode ser útil desenhar em cima dos labirintos de cada exercício. 

[break]

**Exercício**: no labirinto abaixo, a mão está em qual parede? Qual será a próxima casa a ser ocupada? 

```
######
#.....
#...##
#....#
#..o.#
######
```

**Exercício**: no labirinto abaixo, a mão está em qual parede? Qual será a próxima casa a ser ocupada? 

```
##########
.....o....
..........
##########
```

**Exercício**: no labirinto abaixo, suponha que a mão está na parede à direita. Qual será a próxima casa a ser ocupada? A mão continua na mesma parede? 


```
##########
.....o#...
......#...
##########
```


**Exercício**: no labirinto abaixo, suponha que a mão está na parede à direita. Qual será a próxima casa a ser ocupada? A mão continua na mesma parede? 


```
##########
....#o#...
....#.....
#####.####
```

Vamos agora para um caso difícil. Veja o labirinto abaixo.


```
##########
..........
....o#....
.....#....
##########
```

Gostaríamos que o caminho envolvesse "dar a volta" na parede à direita. Isso acontece pois se andarmos à frente não haverá mais nenhuma parede para seguir. Vamos, então dar **dois passos** de uma vez e posicionar a mão na parede abaixo de `o`. Isto está mostrado abaixo. Os `x` representam a posição inicial e o passo anterior dado para resolver este caso.


```
##########
....xo....
....x#....
.....#....
##########
```

Note que agora continuamos na mesma situação, mas rotacionada em sentido horário! Aplicando a mesma ideia novamente teremos contornado a parede e estaremos do outro lado dela. 

[break]

## Alguns exemplos completos

Faça uma simulação da ideia desenvolvida na página anterior para os labirintos abaixo. Você deve traçar o percurso feito em cada labirinto até encontrar a saída. 

```
##########
....o.....
..........
##########
```

[line-spacer]

```
##########
...#......
.....o#...
##########
```

[line-spacer]

```
##########
...#.#....
....o.#...
##########
```

[line-spacer]

## Formalizando nosso algoritmo
    
Agora está na hora de começar a formalizar o algoritmo. O estado do algoritmo é

- linha `i` da posição atual
- coluna`j` da posição atual
- direção `m` da parede da mão direita
  - esse `m` pode ser uma string com as direções


**Exercício**: Como detectamos que a posição atual é uma saída?

[line-spacer]

**Exercício**: E se o labirinto não tiver saída? Como detectamos isso? Para ajudar, desenhe um labirinto simples sem saída. 

[line-spacer]

[line-spacer]

[line-spacer]

**Exercício**: Escreva a condição de parada do algoritmo.

[line-spacer]

[break]

**Exercício**: Para cada posição no labirinto, nosso algoritmo precisa **determinar a próxima posição válida**. Desenhe abaixo todas os casos que devemos considerar para quando a mão está na parede à direita. No lado direito de cada caso, desenhe a ação que deve ser feita.

[spacer]

[spacer]

[spacer]

[line-spacer]

[line-spacer]

**Exercício**: Levando em conta que as 4 direções no labirinto são simétricas, quantos casos precisaremos considerar para cobrir todas as direções?

[line-spacer]

Com isso pronto, implemente sua heurística no exercício do Prairie Learn.

