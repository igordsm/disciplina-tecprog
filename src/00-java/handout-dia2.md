---
title: Condicionais e Loops
subtitle: Técnicas de Programação
author: Igor Montagner
...

::: tip :::
Para cada algoritmo abaixo:

1. leia o pseudo código
2. simule seu funcionamento usando as entradas de exemplo
3. confira o resultado usando os testes no exercício do PrairieLearn
4. use o *CheatSheet* para converter o pseudo código para Java
:::

## Entregador mais próximo

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Encontra o índice $(x_i, y_i)$ mais perto do ponto $o$}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array float $x$, array float $y$, float $o_x$, float $o_y$}
\Output{int}
\BlankLine

$\textbf{int } mprox \gets 0$\;
$\textbf{float } dist\_mprox \gets = \sqrt{(x_0 - o_x)^2 + (y_0 - o_y)^2}$\;
\BlankLine
\For{$i \gets 1 \textbf{ to } x.length$}{
    $\textbf{float }d = \sqrt{(x_i - o_x)^2 + (y_i - o_y)^2}$\;
    \If{$d < dist\_mprox$}{
        $dist\_mprox \gets d$\;
        $mprox \gets i$\;
    }        
}
\Return{$mprox$}
\caption{Entregador mais próximo}
\end{algorithm} 

**Entrada 1**: $o=(0, 0), x=[123, 42 ,10], y=[432, 312, 20]$

[spacer]

**Entrada 2**: $o=(3, 4), x=[10, 4, 4, 23], y=[20, 2, 4, 63]$


## Diferença de listas

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Cria nova lista com diferença entre $A_1$ e $A_2$}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array $A_1$, array $A_2$}
\Output{array $A_3$}
\BlankLine

$count \gets 0$\;
\For{$i \gets 0 \textbf{ to } A_1.length$}{
    $emA_2 \gets \textbf{false}$\;
    \For{$f \gets 0 \textbf{ to } A_2.length$}{
        \If{$A_1[i] = A_2[j]$}{
            $emA_2 \gets \textbf{true}$\;
        }
    }
    \If{$emA_2 = \textbf{false}$}{
        $count \gets count + 1$\;
    }
}
\BlankLine
$A_3 = \textbf{novo array}(count)$\;
$count \gets 0$\;
\For{$i \gets 0 \textbf{ to } A_1.length$}{
    $emA_2 \gets \textbf{false}$\;
    \For{$f \gets 0 \textbf{ to } A_2.length$}{
        \If{$A_1[i] = A_2[j]$}{
            $emA_2 \gets \textbf{true}$\;
        }
    }
    \If{$emA_2 = \textbf{false}$}{
        $A_3[count] = A_1[i]$\;
        $count \gets count + 1$\;
    }
}
\Return{$A_3$}
\caption{DiffListas}
\end{algorithm} 

**Entrada 1**: $A_2 = [1, 2, 3, 4], A_1=[4, 5, 6]$

[spacer]

**Entrada 2**: $A_1 = [1, 2, 3, 4], A_2=[4, 5, 6]$


## Valor da nota

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Valor da Nota}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array float $P$, array float $Q$}
\Output{float}
\BlankLine

$total \gets 0$\;
\For{$i \gets 0 \textbf{ to } P.length$}{
    $total \gets total + P[i] * Q[i]$\;
}
\Return{$total$}
\caption{ValorNota}
\end{algorithm} 

**Entrada 1**: $P=[1.40,1.45,11.4], Q=[1.40,1.45,11.4]$

[spacer]

**Entrada 2**: $P=[1.5], Q=[3]$

[spacer]

**Entrada 3**: $P=[1.21, 1.1, 4.5, 6.1, 100.15, 0.4, 8.67], Q=[13, 41, 63, 6, 52, 14, 47]$

[break]


## Conta Celulares

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Dada uma lista com números de telefone, devolve uma nova lista contendo somente os números que são de celular.}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array string $L$}
\Output{array string}
\BlankLine
$count \gets 0$;
\For{$i \gets 0 \textbf{ to } L.length$}{
    \If{$L[i].length = 14 \textbf{ AND } L[i][5] = '9'$} {
        $count \gets count + 1$\;
    }
    \If{$L[i].length = 11 \textbf{ AND } L[i][2] = '9'$} {
        $count \gets count + 1$\;
    }
    \If{$L[i].length = 9 \textbf{ AND } L[i][0] = '9'$} {
        $count \gets count + 1$\;
    }
}
$res \gets \text{novo array string}[count]$\;
$k \gets 0$\;
\For{$i \gets 0 \textbf{ to } L.length$}{
    \If{$L[i].length = 14 \textbf{ AND } L[i][5] = '9'$} {
        $res[k] \gets L[i]$\;
        $k \gets k + 1$\;
    }
    \If{$L[i].length = 11 \textbf{ AND } L[i][2] = '9'$} {
        $res[k] \gets L[i]$\;
        $k \gets k + 1$\;
    }
    \If{$L[i].length = 9 \textbf{ AND } L[i][0] = '9'$} {
        $res[k] \gets L[i]$\;
        $k \gets k + 1$\;
    }
}
\Return{$res$}\;
\caption{FiltraCelulares}
\end{algorithm} 

**Entrada 1**: $L=[$"+5511912345678", "1155556666", "77778888", "+551133334444", "918273645", "11987654321"$]$

[break]

## Palavras iguais

Agora vamos tentar escrever um pseudo código nosso. Não se esqueça que nossas strings são acessadas igual a um array. Preencha abaixo e verifique se seu algoritmo funciona usando as entradas abaixo.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Verifica se uma string é formada por duas palavras iguais separadas por um caractere '-'}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{string $S$}
\Output{boolean}
\vspace{20em}
\caption{PalavrasIguais}
\end{algorithm} 

**Entrada 1**: $S=$``abc-abc''

[spacer]

**Entrada 2**: $S=$``abc-abca''

[spacer]

**Entrada 3**: $S=$``zig-zag''
