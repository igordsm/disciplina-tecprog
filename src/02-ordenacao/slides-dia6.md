---
footer: 'Igor Montagner (igorsm1@insper.edu.br)'
---

<!-- _class: front -->

# Ordenação Rápida

## Técnicas de Programação

------

# QuickSort

```
QUICKSORT(A, INI, FIM)

IF INI >= FIM - 1 THEN
    RETURN
END

LP = PARTICIONA(A, INI, FIM)
QUICKSORT(A, INI, LP)
QUICKSORT(A, LP+1, FIM)
```

------------

# MERGE-SORT

```
MERGE-SORT(A, AUX, INI, FIM)

IF INI >= FIM - 1 THEN
    RETURN
END

MEIO <- (INI + FIM - 1) / 2
MERGE-SORT(A, AUX, INI, MEIO+1)
MERGE-SORT(A, AUX, MEIO+1, FIM)

MERGE(A, AUX, INI, FIM, MEIO+1)
```

--------------------------------------

# Recursão

## algoritmo que **chama a si mesmo** uma ou mais vezes

## passando uma instância **menor** do problema

--------

# Pensando em recursão

1. Para quais entradas não precisamos fazer chamada recursiva?
2. O programa termina?
3. O programa funciona, supondo que as chamadas recursivas retornam o valor correto?

-------------

<!-- _class: front -->

# Atividades hoje

1. implementação dos algoritmos de ordenação rápida no PrairieLearn
2. dúvidas da PI
