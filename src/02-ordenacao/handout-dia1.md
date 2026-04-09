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


