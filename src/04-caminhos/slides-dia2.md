---
footer: 'Igor Montagner (igorsm1@insper.edu.br)'
---

<!-- _class: front -->

# Caminhos em Labirinto

## Técnicas de Programação

------

```
##########
...#......
.....o#...
##########
```

Tem um caminho até a saída?

------


Tem um caminho até a saída?

```
...........
.....o.....
...#####...
...#####...
...........
...........
```

------------

# Revisão 

## Se eu encostar a mão direita na parede e seguir sempre em frente, eventualmente chego na saída


1. algoritmo da mão direita é complicado....
2. e nem sempre acha a saída!


----------

<!-- _class: front -->

# Busca em Profundidade

----------

# O que é um caminho?

**Definição**: 

----------

# O que é uma vizinhança?

**Definição**: Dado uma casa $c$,

1. $c_E$ é a casa à **e**squerda
1. $c_D$ é a casa à **d**ireita
1. $c_C$ é a casa a**c**ima
1. $c_B$ é a casa a**b**aixo

------

# Definição recursiva

Dadas duas casas $f$ e $d$ e suponhamos que exista caminho entre elas

### O que podemos dizer sobre os vizinhos de $f$ em relação a $d$?

-----------------

# Definição recursiva II

Dadas duas casas $f$ e $d$ e suponhamos que **não** exista caminho entre elas

### O que podemos dizer sobre os vizinhos de $f$ em relação a $d$?

-----------------

# Definição recursiva III

Seja uma função **recursiva** $C$ tem dois argumentos e devolve verdade se existe caminho entre elas. 

$$
C(f, d) =
\begin{align}
\begin{cases} true & se \\
true & se \\[20pt]
false & c.c
\end{cases}
\end{align}
$$

-----------------

# Essa definição é circular?

$$
\exists C(f, d) \Leftrightarrow \exists C(f_E, d) \Leftrightarrow \exists C(f_{E_D}, d) \Leftrightarrow .....
$$

Afinal, $f_{E_D} = f$!

-------------


# Atividade prática: desenvolvendo uma simulação

**Partiremos das conclusões dos slides acima**

