# Arrays Multidimensionais em Java — Parte 02 — For-each

## Introdução

Na aula anterior aprendemos sobre **arrays multidimensionais**.

Nesta aula vamos continuar esse assunto e aprender como utilizar o **for-each** para percorrer arrays multidimensionais.

Também vamos corrigir um pequeno detalhe da aula anterior relacionado ao uso de `length`.

---

# Revisando o `length`

Na aula anterior tínhamos uma estrutura semelhante a esta:

```java
int[][] dias = new int[3][3];
```

E utilizamos algo parecido com:

```java
for (int i = 0; i < dias[0].length; i++) {
    // ...
}
```

Isso funcionava porque, nesse exemplo, todos os arrays internos possuíam três posições.

Porém, essa não é a forma mais correta de fazer.

O ideal é utilizar:

```java
dias[i].length
```

em vez de:

```java
dias[0].length
```

---

# Por que utilizar `dias[i].length`?

Lembre-se de que um array multidimensional é, na prática, um **array que possui referências para outros arrays**.

Por exemplo:

```java
int[][] dias = new int[3][];
```

Podemos ter:

```text
dias
 │
 ├── posição 0 → array com 3 posições
 ├── posição 1 → array com 5 posições
 └── posição 2 → array com 2 posições
```

Nesse caso, cada posição pode fazer referência a um array de tamanho diferente.

Portanto:

```java
dias[0].length
```

retorna o tamanho do array da posição `0`.

Já:

```java
dias[1].length
```

retorna o tamanho do array da posição `1`.

E:

```java
dias[2].length
```

retorna o tamanho do array da posição `2`.

Por isso, quando estamos percorrendo o array com um `for`, o correto é utilizar:

```java
dias[i].length
```

Assim, o tamanho será obtido de acordo com a posição atual.

---

# Estrutura do array multidimensional

Considere:

```java
int[][] dias = new int[3][];
```

Podemos imaginar:

```text
dias
 │
 ├── [0] ──► [ ][ ][ ]
 │
 ├── [1] ──► [ ][ ][ ][ ][ ]
 │
 └── [2] ──► [ ][ ]
```

Nesse caso:

```text
dias[0].length → 3
dias[1].length → 5
dias[2].length → 2
```

Se utilizarmos:

```java
for (int i = 0; i < dias.length; i++) {

    for (int j = 0; j < dias[i].length; j++) {
        // ...
    }
}
```

o segundo `for` sempre utilizará o tamanho correto do array interno.

---

# For-each em arrays multidimensionais

Agora vamos utilizar o `for-each`.

Na aula anterior aprendemos que, para um array simples:

```java
int[] numeros = {1, 2, 3};
```

podemos fazer:

```java
for (int num : numeros) {
    System.out.println(num);
}
```

A variável `num` é do tipo `int` porque cada posição do array contém um `int`.

Porém, em um array multidimensional, a situação é diferente.

---

# Qual é o tipo de cada posição?

Considere:

```java
int[][] dias;
```

A primeira dimensão é um array de arrays.

Ou seja, cada posição de:

```java
dias
```

não contém diretamente um `int`.

Cada posição contém uma **referência para um array de `int`**.

Podemos visualizar:

```text
dias
 │
 ├── posição 0 → int[]
 ├── posição 1 → int[]
 └── posição 2 → int[]
```

Portanto, no primeiro `for-each`, a variável precisa ser do tipo:

```java
int[]
```

---

# Primeiro `for-each`

Podemos fazer:

```java
for (int[] arrayBase : dias) {
    // ...
}
```

Aqui:

```java
int[] arrayBase
```

é uma variável de referência temporária que recebe cada um dos arrays internos.

A estrutura:

```java
for (int[] arrayBase : dias)
```

pode ser entendida como:

> Para cada array de inteiros existente dentro de `dias`, coloque esse array na variável `arrayBase`.

---

# Entendendo a variável `arrayBase`

Imagine:

```text
dias
 │
 ├── posição 0 ──► [1, 2, 3]
 ├── posição 1 ──► [4, 5, 6]
 └── posição 2 ──► [7, 8, 9]
```

Quando o `for-each` começa:

```java
for (int[] arrayBase : dias)
```

na primeira interação:

```text
arrayBase ──► [1, 2, 3]
```

Na segunda:

```text
arrayBase ──► [4, 5, 6]
```

Na terceira:

```text
arrayBase ──► [7, 8, 9]
```

A variável `arrayBase` vai fazendo referência temporariamente a cada array interno.

---

# Segundo `for-each`

Agora que temos:

```java
int[] arrayBase
```

podemos utilizar outro `for-each` para percorrer os elementos desse array.

```java
for (int[] arrayBase : dias) {

    for (int num : arrayBase) {
        System.out.println(num);
    }
}
```

Temos dois `for-each`.

O primeiro percorre os arrays internos.

O segundo percorre os valores existentes dentro de cada array.

---

# Entendendo os dois `for-each`

Observe:

```java
for (int[] arrayBase : dias) {

    for (int num : arrayBase) {
        System.out.println(num);
    }
}
```

O primeiro:

```java
for (int[] arrayBase : dias)
```

percorre:

```text
array 0
array 1
array 2
```

O segundo:

```java
for (int num : arrayBase)
```

percorre os elementos de cada array.

---

# Execução passo a passo

Considere:

```java
int[][] dias = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

Primeiro o `for-each` pega:

```text
arrayBase → {1, 2, 3}
```

Então o segundo `for-each` percorre:

```text
1
2
3
```

Depois o primeiro `for-each` passa para o próximo array:

```text
arrayBase → {4, 5, 6}
```

O segundo percorre:

```text
4
5
6
```

Depois:

```text
arrayBase → {7, 8, 9}
```

E o segundo percorre:

```text
7
8
9
```

Resultado final:

```text
1
2
3
4
5
6
7
8
9
```

---

# Código completo

```java
int[][] dias = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

for (int[] arrayBase : dias) {

    for (int num : arrayBase) {
        System.out.println(num);
    }
}
```

---

# O que acontece por baixo dos panos?

É importante entender o funcionamento das variáveis de referência.

No primeiro `for-each`:

```java
for (int[] arrayBase : dias)
```

a variável:

```java
arrayBase
```

é uma variável de referência do tipo:

```java
int[]
```

Ela recebe, a cada interação, a referência para um dos arrays internos.

Podemos imaginar:

### Primeira interação

```text
arrayBase ──► dias[0]
```

### Segunda interação

```text
arrayBase ──► dias[1]
```

### Terceira interação

```text
arrayBase ──► dias[2]
```

---

# O segundo `for-each`

Depois temos:

```java
for (int num : arrayBase)
```

Nesse momento:

```java
arrayBase
```

já está fazendo referência a um dos arrays internos.

Por exemplo:

```text
arrayBase ──► [1, 2, 3]
```

Então o segundo `for-each` percorre:

```text
1
2
3
```

Quando a primeira iteração termina, o primeiro `for-each` muda a referência:

```text
arrayBase ──► [4, 5, 6]
```

E o segundo `for-each` percorre:

```text
4
5
6
```

E assim por diante.

---

# Comparando com o `for` tradicional

Podemos percorrer um array multidimensional utilizando `for` tradicional:

```java
for (int i = 0; i < dias.length; i++) {

    for (int j = 0; j < dias[i].length; j++) {
        System.out.println(dias[i][j]);
    }
}
```

Ou utilizando `for-each`:

```java
for (int[] arrayBase : dias) {

    for (int num : arrayBase) {
        System.out.println(num);
    }
}
```

Os dois códigos podem produzir o mesmo resultado.

---

# Diferença entre as duas formas

## `for` tradicional

```java
for (int i = 0; i < dias.length; i++) {

    for (int j = 0; j < dias[i].length; j++) {
        System.out.println(dias[i][j]);
    }
}
```

Temos acesso aos índices:

```text
i
j
```

Isso permite saber exatamente qual é a posição que estamos acessando.

---

## `for-each`

```java
for (int[] arrayBase : dias) {

    for (int num : arrayBase) {
        System.out.println(num);
    }
}
```

Não precisamos controlar os índices.

O Java percorre automaticamente:

```text
array → elemento
```

Essa abordagem deixa o código mais simples quando não precisamos trabalhar diretamente com as posições.

---

# Uma forma de visualizar

Podemos imaginar o primeiro `for-each`:

```java
for (int[] arrayBase : dias)
```

como:

```text
dias
 │
 ├──► arrayBase
 │
 ├──► arrayBase
 │
 └──► arrayBase
```

E o segundo:

```java
for (int num : arrayBase)
```

como:

```text
arrayBase
 │
 ├──► num
 ├──► num
 └──► num
```

Ou seja:

```text
Array multidimensional
        │
        ▼
   Array interno
        │
        ▼
      Valor
```

---

# Exemplo visual completo

Considere:

```java
int[][] dias = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

Temos:

```text
dias
 │
 ├──► {1, 2, 3}
 │       │
 │       ├──► 1
 │       ├──► 2
 │       └──► 3
 │
 ├──► {4, 5, 6}
 │       │
 │       ├──► 4
 │       ├──► 5
 │       └──► 6
 │
 └──► {7, 8, 9}
         │
         ├──► 7
         ├──► 8
         └──► 9
```

O primeiro `for-each` percorre:

```text
{1, 2, 3}
{4, 5, 6}
{7, 8, 9}
```

O segundo percorre os elementos de cada um:

```text
1 2 3
4 5 6
7 8 9
```

---

# Resumo

Nesta aula aprendemos:

* Arrays multidimensionais são arrays que possuem outros arrays.
* Cada posição do array principal contém uma referência para um array interno.
* Por isso, em:

```java
int[][] dias;
```

cada elemento da primeira dimensão é do tipo:

```java
int[]
```

* No primeiro `for-each`, devemos utilizar:

```java
for (int[] arrayBase : dias)
```

* A variável `arrayBase` é uma referência temporária para cada array interno.
* Depois podemos utilizar outro `for-each`:

```java
for (int num : arrayBase)
```

* O segundo `for-each` percorre os valores dentro do array interno.
* Para percorrer um array multidimensional com `for-each`, normalmente utilizamos um `for-each` dentro de outro.

---

# Estrutura principal para memorizar

Para um array simples:

```java
int[] numeros;

for (int num : numeros) {
    System.out.println(num);
}
```

Para um array multidimensional:

```java
int[][] numeros;

for (int[] arrayBase : numeros) {

    for (int num : arrayBase) {
        System.out.println(num);
    }
}
```

A diferença principal está no **tipo da primeira variável**.

Array simples:

```java
int num
```

Array multidimensional:

```java
int[] arrayBase
```

Isso acontece porque cada posição do array multidimensional é, por sua vez, um **array de inteiros**.

---

# `length` no array multidimensional

Quando utilizamos o `for` tradicional, lembre-se de utilizar o tamanho do array correspondente à posição atual:

```java
for (int i = 0; i < dias.length; i++) {

    for (int j = 0; j < dias[i].length; j++) {
        System.out.println(dias[i][j]);
    }
}
```

Evite assumir que todos os arrays internos possuem o mesmo tamanho utilizando algo como:

```java
dias[0].length
```

quando a intenção é percorrer cada posição.

O correto é:

```java
dias[i].length
```

porque o tamanho deve acompanhar o array interno que está sendo percorrido.

---

> **Dica:** ao estudar arrays multidimensionais, pense sempre em três níveis: **array principal → array interno → elemento**. Essa visualização facilita bastante a compreensão do `for-each` aninhado.
