# Persistência Parcial

O objetivo do trabalho é implementar uma estrutura de dados que suporta persistência parcial seguindo o método descrito em sala.
A sua implementação **não pode** fazer uma cópia inteira da estrutura a cada modificação.

Equipes da graduação devem implementar uma lista encadeada ordenada com persistência parcial.
Equipes da pós-graduação devem implementar uma árvore binária de busca com persistência parcial (**não** precisa ser auto-balanceável, como as árvores AVL ou rubro-negras).

## Operações

As estruturas devem suportar as seguintes operações:

- **Inclusão:** Uma operação de inclusão será identificada por uma linha como ```INC N```.
Isto significa que um elemento com chave N deve ser incluído na estrutura e uma nova versão criada.

Exemplo de linha de inclusão:

```INC 13```

- **Remoção:** Uma operação de remoção será identificada por uma linha como ```REM N```.
Um elemento com este valor deve ser removido (apenas um se houver repetição).
Caso não haja um nó com o valor especificado, a estrutura não deve ser alterada.
Em ambos os casos uma nova versão deve ser criada.

Exemplo de linha de remoção:

```REM 17```

- **Sucessor:** Uma operação de sucessor será identificada por uma linha como ```SUC N M```.
A linha de entrada deve ser impressa e, em seguida, a chave com menor valor que é estritamente maior que ```N``` na versão ```M``` da estrutura deve ser impressa uma linha abaixo.
Não é necessário existir um elemento com chave ```N``` na estrutura para que a operação de sucessor seja feita.
Essa operação não deve criar uma nova versão na estrutura.

Exemplo de linha de sucessor:

```SUC 2 20```

Exemplo dessa linha na impressão de saída:

```
SUC 2 20
3
```

- **Imprimir:** Uma operação de impressão será identificada por uma linha como ```IMP M```.
A linha de entrada deve ser impressa e, em seguida, os elementos da estrutura na versão ```M``` devem ser impressos na linha abaixo em ordem crescente, separados por vírgula e espaço.
Caso a versão fornecida não exista, a impressão deve ocorrer na versão mais recente.
Essa operação não deve criar uma nova versão na estrutura.

Exemplo de linha de impressão:

```IMP 20```

Exemplo dessa linha na impressão de saída:

```
IMP 20
1, 3, 5, 7, 9
```

## Versões:

A estrutura deve começar na versão 0.
Cada operação de inclusão e remoção aumenta a versão da estrutura em 1.
Haverá no máximo 99 operações de inclusão e remoção, de modo que haverá no máximo 100 versões diferentes da estrutura, então os identificadores das versões (raiz da estrutura e em quais versões ela opera) podem ser guardados num vetor de tamanho 100.
Não há limite para o número de operações de sucessor e de impressão, mas estas não criam novas versões.
