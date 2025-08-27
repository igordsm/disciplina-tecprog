---
title: Algoritimos (simples) de Ordenação
subtitle: Técnicas de Programação
author: Igor Montagner
...

Em um primeiro momento, estudaremos dois algoritmos simples de ordenação: *Bubble Sort* e *Selection Sort*. Um dos nossos objetivos aqui é contar o número de **comparações** feitas por esses algoritmos, sempre considerando o **pior caso**.


# Bubble Sort

Considere o algoritmo abaixo para as próximas perguntas.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array $A$}
\Output{}

$\text{trocou} \gets \textbf{true}$\;
$C \gets 0$\;
\BlankLine
\While{$\text{trocou} = \textbf{true}$}{
    $\text{trocou} \gets \textbf{false}$\;
    \For{$i \gets 0 \textbf{ to } A.length - 1$}{
        \If{$A[i] > A[i+1]$}{
            $\text{trocar valores entre } A[i] \text{ e } A[i+1]$\;
            $\text{trocou} \gets \textbf{true}$\;
        }
    }
    $C \gets C + 1$\;
}
\caption{BubbleSort}
\end{algorithm} 

Nosso objetivo será entender esse algoritmo somente **simulando seu funcionamento**. Sabemos que ele ordena o array $A$, mas o ponto aqui é entende **como** ele faz isso. 

**Exercício**: Para o array $A = [  3, 4, 2 , 5, 77, 8, 12 ]$, simule a primeira iteração do loop *while*. Escreva abaixo o valor final de $A, C$ e $\text{trocou}$.

[spacer]

**Exercício**: Faça o mesmo para o array $A = [  8, 7, 6, 5, 4, 3, 2, 1 ]$.

[break]

**Exercício**: Faça o mesmo para o array $A = [  10, 20, 30, 40, 50, 60, 70, 80 ]$. O que você notou de diferente em relação aos anteriores?

[line-spacer]

[line-spacer]

------------------

**Exercício**: Começando agora com o array $A = [  3, 4, 2 , 5, 77, 8, 12 ]$, preencha a tabela abaixo. Cada linha corresponde a uma vez que foi feita uma troca de duas posições vizinhas. As primeiras duas linhas já estão preenchidas.

| $C$           | $i$           | $A$                                    |
|---------------|---------------|----------------------------------------|
| 0\hspace{1em} | 1\hspace{1em} | $[3, 2, 4, 5, 77, 8, 12 ]$\hspace{1em} |
| 0             | 4             | $[3, 2, 4, 5, 8, 77, 12 ]$             |
|               |               |                                        |
|               |               |                                        |
|               |               |                                        |
|               |               |                                        |
|               |               |                                        |
|               |               |                                        |
|               |               |                                        |

**Exercício**: Começando agora com o array $A = [ 5, 4, 7, 2, 9, 7, 11, 32, 4 ]$, preencha a tabela abaixo. Cada linha corresponde a uma vez que foi feita uma troca de duas posições vizinhas. As primeiras duas linhas já estão preenchidas.

| $C$                | $i$                | $A$                                                                |
|--------------------|--------------------|--------------------------------------------------------------------|
| &nbsp;\hspace{3em} | &nbsp;\hspace{3em} | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |



[break]

Vamos agora tentar entender o número máximo de operações feitas por este algoritmo. Para isso, vamos usar o array ordenado em ordem **decrescente** como exemplo. Dado que ele está totalmente ao contrário, é um bom exemplo para testar algoritmos de ordenação.

**Exercício**: Começando agora com o array $A = [ 5, 4, 3, 2, 1 ]$, preencha a tabela abaixo. Cada linha corresponde a uma vez que foi feita uma troca de duas posições vizinhas.

| $C$                | $i$                | $A$                                                                |
|--------------------|--------------------|--------------------------------------------------------------------|
| &nbsp;\hspace{3em} | &nbsp;\hspace{3em} | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |
|                    |                    |                                                                    |

**Exercício**: O algoritmo fez quantas trocas no exemplo acima? Se a entrada tivesse tamanho $N=6$, quantas você acha que ele faria? Use esse raciocínio para estimar o número de trocas feitas para entradas de tamanho $N > 0$ quaisquer.

[line-spacer]

[line-spacer]

Agora que entendemos melhor o algoritmo, vamos implementá-lo no PrairieLearn. Como bônus, assistam o vídeo abaixo e tentem relacioná-lo com a execução do algoritmo no início desta atividade. 

![qr bubble sort](qr-bubble-sort.png){ height=130px }

<!---

Agora que simulamos uma vez, podemos ver um vídeo desse algoritmo funcionando para o array `[ 3 0 1 8 7 2 5 4 6 9 ]`

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/Iv3vgjM8Pv4?si=gtTqR-MNNrGmJH-B" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


!!! exercise long id_bubble_explicacao
    Agora que você simulou o algoritmo para algumas entradas, consegue explicar **como** ele funciona e **por que** o array chega no fim ordenado? Escreva abaixo

    !!! answer
        Discutido em sala. Use a opção "Editar" para modificar suas anotações após a discussão. 

## Selection Sort

Vamos agora desenvolver um algoritmo a partir de uma ideia de alto nível:

1. Comece encontrando o menor elemento do array. Troque ele de posição com o elemento na posição `0`. 
2. Faça o mesmo para a posição `1`, mas procurando o mínimo agora a partir do elemento `1`. Troque esse elemento com o da posição `1`
3. Repita isso para todas as posições do array, sempre tomando cuidado para pegar o mínimo da porção à direita da posição atual.

Vamos agora simular essa ideia para entendê-la melhor. 

!!! exercise long id_selection_algo_caso1
    Simule a ideia acima para o array `A = [3, 5, 4, 2]`. Você deve colocar uma linha para cada iteração do algoritmo, ou seja, cada vez que é feita uma troca entre o elemento atual e o menor da porção que resta do array. Em cada linha escreva

    - os índices que são feitas a troca
    - o estado de `A` após a troca ser feita. 

    !!! answer
        A lista abaixo está ordenada pelo índice do elemento analisado

        0. O menor elemento de A é 2, então fazemos a troca entre o índice `0` e o índice `3`. `A = [2, 5, 4, 3]`
        1. O menor elemento de A (a partir do índice 1) é 3. É feita troca entre os índices `1` e `3`. `A = [2, 3, 4, 5]`
        2. O menor elemento de A (a partir do índice 2) é 4. É feita troca entre os índices `2` e `2`. `A = [2, 3, 4, 5]`

        Quando chegamos no índice `3` a porção restante de `A` só tem um elemento, então terminamos aqui. 



!!! exercise long id_selection_algo_caso2
    Simule a ideia acima para o array `A = [5, 6, 8, 11]`. Você deve colocar uma linha para cada iteração do algoritmo, ou seja, cada vez que é feita uma troca entre o elemento atual e o menor da porção que resta do array. Em cada linha escreva

    - os índices que são feitas a troca
    - o estado de `A` após a troca ser feita. 

    !!! answer
        A lista abaixo está ordenada pelo índice do elemento analisado

        0. O menor elemento de A é 5, então fazemos a troca entre o índice `0` e o índice `0`. `A = [5, 6, 8, 11]`
        1. O menor elemento de A (a partir do índice 1) é 6. É feita troca entre os índices `1` e `1`. `A = [5, 6, 8, 11]`
        2. O menor elemento de A (a partir do índice 2) é 8. É feita troca entre os índices `2` e `2`. `A = [5, 6, 8, 11]`

        Quando chegamos no índice `3` a porção restante de `A` só tem um elemento, então terminamos aqui. 



!!! exercise long id_selection_algo_caso3
    Simule a ideia acima para o array `A = [3, 7, 12, 0, -1, 4, 8]`. Você deve colocar uma linha para cada iteração do algoritmo, ou seja, cada vez que é feita uma troca entre o elemento atual e o menor da porção que resta do array. Em cada linha escreva

    - os índices que são feitas a troca
    - o estado de `A` após a troca ser feita. 

    !!! answer
        A lista abaixo está ordenada pelo índice do elemento analisado

        0. O menor elemento de A (a partir do índice 0) é -1. É feita troca entre os índices `0` e `4`. `A = [-1, 7, 12, 0, 3, 4, 8]`
        1. O menor elemento de A (a partir do índice 1) é 0. É feita troca entre os índices `1` e `3`. `A = [-1, 0, 12, 7, 3, 4, 8]`
        2. O menor elemento de A (a partir do índice 2) é 3. É feita troca entre os índices `2` e `4`. `A = [-1, 0, 3, 7, 12, 4, 8]`
        3. O menor elemento de A (a partir do índice 3) é 4. É feita troca entre os índices `3` e `5`. `A = [-1, 0, 3, 4, 12, 7, 8]`
        4. O menor elemento de A (a partir do índice 4) é 7. É feita troca entre os índices `4` e `5`. `A = [-1, 0, 3, 4, 7, 12, 8]`
        5. O menor elemento de A (a partir do índice 5) é 8. É feita troca entre os índices `5` e `6`. `A = [-1, 0, 3, 4, 7, 8, 12]`

        Quando chegamos no índice `6` a porção restante de `A` só tem um elemento, então terminamos aqui. 

Novamente, veja um vídeo da simulação para o array `[ 3 0 1 8 7 2 5 4 9 6 ]`

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/0-W8OEwLebQ?si=PN9Ro-0npBBedByK" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


Agora que já simulamos o algoritmo algumas vezes, vamos escrever o pseudo código dele.

!!! exercise long id_selection_algo_write
    Escreva abaixo o pseudo-código de `SELECTION_SORT(A)`. 

    !!! answer
        Discutido em sala. Use a opção "Editar" para modificar suas anotações após a discussão. 

## Considerações sobre eficiência 

Os algoritmos acima são bem diferentes entre si. 

!!! exercise long id_bubble_complexidade
    Responda às seguintes perguntas levando em conta o algoritmo `BUBBLE_SORT` da primeira seção. Para cada uma você deve escrever a resposta em termos do tamanho do `N` do array `A`.

    1. no pior caso, quantas vezes roda o loop `ENQUANTO`?
    2. e o loop interno, roda quantas vezes?

    Junte essas duas informações e diga, no pior caso, quantas operações são feitas pelo algoritmo. 
    
    **Dica**: tente contar quantas vezes a comparação `A[I] > A[I+1]` é executada. 

    !!! answer 
        Discutido em sala. Use a opção "Editar" para modificar suas anotações após a discussão. 


!!! exercise long id_selection_complexidade
    Responda às seguintes perguntas levando em conta o algoritmo `SELECTION_SORT` da segunda seção. Para cada uma você deve escrever a resposta em termos do tamanho do `N` do array `A`.

    1. quantas vezes é executado o processo de encontrar o menor valor do array?
    2. qual o custo, no pior caso, de encontrar o menor valor de uma porção do array?

    Junte essas duas informações e diga, no pior caso, quantas operações são feitas pelo algoritmo. 

    !!! answer 
        Discutido em sala. Use a opção "Editar" para modificar suas anotações após a discussão. 

!!! exercise long
    Mostre (usando a aula [01-02 Desempenho](../../../modulos/01-Busca-Array/desempenho)) que ambos algoritmos crescem de maneira equivalente.

    !!! answer
        Discutir no atendimento esse aqui ;)

-->
