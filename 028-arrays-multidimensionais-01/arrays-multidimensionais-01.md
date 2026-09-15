# Arrays Multidimensionais em Java — Parte 01

## Introdução

Nesta aula vamos continuar os estudos sobre arrays e aprender o conceito de **arrays multidimensionais**.

Um array multidimensional pode ser entendido, de forma simplificada, como um **array que possui outros arrays dentro dele**.

Em outras palavras:

```text
Array
 ├── Array
 ├── Array
 └── Array
```

Isso permite trabalhar com estruturas que possuem mais de uma dimensão.

Um exemplo bastante comum é uma estrutura semelhante a uma **tabela**, formada por linhas e colunas.

---

# Um problema para entender o conceito

Imagine que queremos armazenar informações sobre os **dias de cada mês do ano**.

Temos 12 meses:

```text
Janeiro
Fevereiro
Março
Abril
Maio
Junho
Julho
Agosto
Setembro
Outubro
Novembro
Dezembro
```

Podemos ter um primeiro array com 12 posições, onde cada posição representa um mês.

Por exemplo:

```text
Índice →  0    1    2    3   ...   11
Mês    → Jan  Fev  Mar  Abr  ...  Dez
```

Porém, cada mês possui uma quantidade diferente de dias.

Por exemplo:

```text
Janeiro    → 31 dias
Fevereiro  → 28 dias
Março      → 31 dias
Abril      → 30 dias
...
```

Então precisamos de uma estrutura que permita relacionar cada mês com a quantidade de dias correspondente.

É nesse cenário que podemos utilizar um **array multidimensional**.

---

# O que é um array multidimensional?

Um array multidimensional é uma estrutura que possui **arrays dentro de arrays**.

Podemos imaginar:

```text
Array principal
│
├── Array 0
├── Array 1
└── Array 2
```

Cada posição do array principal pode fazer referência a outro array.

Por exemplo:

```java
int[][] numeros;
```

Os dois pares de colchetes:

```java
[][]
```

indicam que estamos trabalhando com duas dimensões.

---

# Criando um array bidimensional

Podemos criar um array bidimensional da seguinte forma:

```java
int[][] numeros = new int[3][3];
```

Nesse caso, temos:

* Um array principal com **3 posições**.
* Cada posição referencia outro array.
* Cada um desses arrays possui **3 posições**.

Podemos visualizar:

```text
             Array principal

              +-----+-----+-----+
              |  ?  |  ?  |  ?  |
              +-----+-----+-----+
                0     1     2
                │     │     │
                ▼     ▼     ▼
              Array Array Array
                │     │     │
                ▼     ▼     ▼
              [ ][ ] [ ][ ] [ ][ ]
```

Cada posição do array principal referencia outro array.

---

# Visualizando como uma matriz

Também podemos visualizar o array bidimensional como uma tabela:

```text
       Colunas
       0   1   2
     +---+---+---+
  0  | 0 | 0 | 0 |
     +---+---+---+
  1  | 0 | 0 | 0 |
     +---+---+---+
  2  | 0 | 0 | 0 |
     +---+---+---+
```

Temos:

* 3 linhas.
* 3 colunas.
* 9 posições no total.

O valor padrão dos elementos `int` é `0`.

---

# Array de arrays

Uma maneira interessante de entender:

```java
int[][] numeros = new int[3][3];
```

é pensar que estamos criando:

```text
Um array
   │
   ├── outro array
   ├── outro array
   └── outro array
```

Cada posição do primeiro array não guarda diretamente um `int`.

Ela guarda uma **referência para outro array**.

Podemos representar:

```text
numeros
   │
   ▼
+--------+--------+--------+
|   ↗    |   ↗    |   ↗    |
+--------+--------+--------+
    │        │        │
    ▼        ▼        ▼
 [0 0 0]  [0 0 0]  [0 0 0]
```

---

# Dimensões

Quando temos:

```java
int[] numeros;
```

temos uma dimensão.

Quando temos:

```java
int[][] numeros;
```

temos duas dimensões.

Podemos continuar adicionando dimensões:

```java
int[][][] numeros;
```

Nesse caso, temos três dimensões.

E assim por diante.

Porém, para entender o conceito, vamos trabalhar inicialmente com **duas dimensões**.

---

# Sintaxe recomendada

Para declarar um array multidimensional, utilizamos os colchetes dessa forma:

```java
int[][] numeros;
```

É possível escrever os colchetes de outras maneiras na declaração, mas a forma mais recomendada e mais clara é:

```java
int[][] numeros;
```

Ou seja, mantenha os colchetes juntos ao tipo.

---

# Criando um array multidimensional

Podemos criar:

```java
int[][] numeros = new int[3][3];
```

Aqui temos:

```text
3 arrays
   ↓
cada um possui 3 posições
```

Visualmente:

```text
Linha 0 → [0][0][0]
Linha 1 → [0][0][0]
Linha 2 → [0][0][0]
```

---

# O primeiro tamanho é obrigatório?

Uma característica importante dos arrays multidimensionais em Java é que podemos criar a primeira dimensão sem definir imediatamente o tamanho das dimensões seguintes.

Por exemplo:

```java
int[][] numeros = new int[3][];
```

Essa declaração é válida.

Estamos dizendo:

> Quero um array principal com 3 posições, mas os arrays internos ainda não foram definidos.

Podemos visualizar:

```text
numeros
   │
   ▼
+-----+-----+-----+
|  ?  |  ?  |  ?  |
+-----+-----+-----+
   0     1     2
```

Nesse momento, as posições ainda não possuem arrays internos associados.

---

# Definindo os arrays internos posteriormente

Depois podemos criar os arrays internos:

```java
numeros[0] = new int[3];
numeros[1] = new int[3];
numeros[2] = new int[3];
```

Agora teremos:

```text
numeros
   │
   ├── numeros[0] → [0][0][0]
   ├── numeros[1] → [0][0][0]
   └── numeros[2] → [0][0][0]
```

Cada posição do array principal referencia outro array.

---

# Arrays internos podem ter tamanhos diferentes

Uma característica interessante é que os arrays internos não precisam necessariamente possuir o mesmo tamanho.

Por exemplo:

```java
int[][] numeros = new int[3][];

numeros[0] = new int[2];
numeros[1] = new int[3];
numeros[2] = new int[4];
```

Podemos ter:

```text
Linha 0 → [0][0]
Linha 1 → [0][0][0]
Linha 2 → [0][0][0][0]
```

Isso acontece porque, em Java, um array multidimensional é, na realidade, um **array de referências para outros arrays**.

Essa característica permite criar estruturas chamadas de **arrays irregulares (jagged arrays)**.

---

# Acessando elementos

Para acessar um elemento de um array bidimensional, utilizamos dois índices.

Por exemplo:

```java
int[][] numeros = new int[3][3];
```

Podemos acessar:

```java
numeros[0][0]
```

O primeiro índice indica o array interno.

O segundo indica a posição dentro desse array.

Podemos pensar:

```text
numeros[linha][coluna]
```

Por exemplo:

```java
numeros[0][0]
```

significa:

```text
Primeiro array
     ↓
    [0]
     ↓
Primeira posição
```

---

# Exemplo de acesso

Considere:

```java
int[][] dias = new int[3][3];
```

Podemos acessar:

```java
dias[0][0]
```

Como os valores padrão de `int` são `0`, teremos:

```text
dias[0][0] → 0
```

Podemos atribuir um valor:

```java
dias[0][0] = 31;
```

Agora:

```text
dias[0][0] → 31
```

---

# Preenchendo uma matriz

Podemos preencher diferentes posições:

```java
int[][] dias = new int[3][3];

dias[0][0] = 31;
dias[0][1] = 28;
dias[0][2] = 31;
```

Podemos visualizar:

```text
Linha 0 → [31][28][31]
Linha 1 → [ 0][ 0][ 0]
Linha 2 → [ 0][ 0][ 0]
```

---

# Dois índices

Quando trabalhamos com duas dimensões, precisamos pensar em dois índices:

```java
dias[i][j]
```

O primeiro índice:

```text
i
```

representa uma posição no array principal.

O segundo:

```text
j
```

representa uma posição dentro do array referenciado.

Podemos visualizar:

```text
dias[i][j]
     │ │
     │ └── posição do array interno
     └──── posição do array principal
```

---

# Percorrendo um array multidimensional

Para percorrer todas as posições, precisamos utilizar **dois `for`**.

Um `for` será responsável por percorrer o array principal.

O segundo `for` percorrerá o array interno.

Exemplo:

```java
int[][] numeros = new int[3][3];

for (int i = 0; i < numeros.length; i++) {

    for (int j = 0; j < numeros[i].length; j++) {
        System.out.println(numeros[i][j]);
    }
}
```

---

# Entendendo os dois `for`

Temos o primeiro:

```java
for (int i = 0; i < numeros.length; i++) {
```

Ele percorre o array principal.

Se temos três posições:

```text
i = 0
i = 1
i = 2
```

Para cada posição de `i`, entramos no segundo `for`:

```java
for (int j = 0; j < numeros[i].length; j++) {
```

O `j` percorre o array interno daquela posição.

---

# Ordem das iterações

Imagine:

```java
int[][] numeros = new int[3][3];
```

A execução ocorrerá dessa forma:

```text
i = 0
    j = 0
    j = 1
    j = 2

i = 1
    j = 0
    j = 1
    j = 2

i = 2
    j = 0
    j = 1
    j = 2
```

Podemos representar:

```text
[0][0]
[0][1]
[0][2]

[1][0]
[1][1]
[1][2]

[2][0]
[2][1]
[2][2]
```

O `for` interno é executado completamente antes que o `for` externo avance para a próxima posição.

---

# Exemplo prático

```java
int[][] numeros = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

for (int i = 0; i < numeros.length; i++) {

    for (int j = 0; j < numeros[i].length; j++) {
        System.out.println(numeros[i][j]);
    }
}
```

A execução será:

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

A ordem dos acessos será:

```text
[0][0] → 1
[0][1] → 2
[0][2] → 3

[1][0] → 4
[1][1] → 5
[1][2] → 6

[2][0] → 7
[2][1] → 8
[2][2] → 9
```

---

# Por que utilizar `numeros[i].length`?

Observe o segundo `for`:

```java
for (int j = 0; j < numeros[i].length; j++) {
```

Não utilizamos simplesmente:

```java
j < 3
```

porque cada array interno pode possuir um tamanho diferente.

Por exemplo:

```java
int[][] numeros = new int[3][];

numeros[0] = new int[2];
numeros[1] = new int[3];
numeros[2] = new int[4];
```

Nesse caso:

```text
numeros[0].length → 2
numeros[1].length → 3
numeros[2].length → 4
```

Portanto, utilizar:

```java
numeros[i].length
```

faz com que o código utilize o tamanho correto de cada array interno.

---

# Exemplo com tamanhos diferentes

```java
int[][] numeros = new int[3][];

numeros[0] = new int[2];
numeros[1] = new int[3];
numeros[2] = new int[4];

for (int i = 0; i < numeros.length; i++) {

    for (int j = 0; j < numeros[i].length; j++) {
        System.out.println(numeros[i][j]);
    }
}
```

Podemos visualizar:

```text
Linha 0 → [0][0]

Linha 1 → [0][0][0]

Linha 2 → [0][0][0][0]
```

O primeiro `for` percorre as linhas.

O segundo percorre as posições de cada linha.

---

# Entendendo a referência para outro array

Essa é uma das partes mais importantes do conceito.

Quando fazemos:

```java
int[][] numeros = new int[3][3];
```

o primeiro array possui três posições.

Cada uma dessas posições faz referência a outro array.

Podemos representar:

```text
numeros
   │
   ▼
+-------+-------+-------+
|   ↗   |   ↗   |   ↗   |
+-------+-------+-------+
    │       │       │
    ▼       ▼       ▼

 [0][0][0]

 [0][0][0]

 [0][0][0]
```

Portanto, quando fazemos:

```java
numeros[0]
```

não estamos obtendo diretamente um número.

Estamos obtendo uma referência para outro array.

Já:

```java
numeros[0][0]
```

acessa uma posição dentro desse array.

---

# Exemplo visual

Podemos pensar:

```text
numeros
   │
   ▼
posição 0 ───────► [0][0][0]
posição 1 ───────► [0][0][0]
posição 2 ───────► [0][0][0]
```

Então:

```java
numeros[0]
```

retorna o primeiro array.

E:

```java
numeros[0][1]
```

retorna o segundo elemento desse primeiro array.

---

# Exemplo completo

```java
public class Aula36 {

    public static void main(String[] args) {

        int[][] numeros = new int[3][3];

        numeros[0][0] = 1;
        numeros[0][1] = 2;
        numeros[0][2] = 3;

        numeros[1][0] = 4;
        numeros[1][1] = 5;
        numeros[1][2] = 6;

        numeros[2][0] = 7;
        numeros[2][1] = 8;
        numeros[2][2] = 9;

        for (int i = 0; i < numeros.length; i++) {

            for (int j = 0; j < numeros[i].length; j++) {
                System.out.println(numeros[i][j]);
            }
        }
    }
}
```

Saída:

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

# Como pensar em arrays multidimensionais

Uma boa maneira de entender esse conceito é **desenhar a estrutura no papel**.

Ao invés de pensar somente no código:

```java
int[][] numeros = new int[3][3];
```

desenhe:

```text
numeros
   │
   ├──► [0][0][0]
   │
   ├──► [0][0][0]
   │
   └──► [0][0][0]
```

Depois pense nos índices:

```text
numeros[0][0]
numeros[0][1]
numeros[0][2]

numeros[1][0]
numeros[1][1]
numeros[1][2]

numeros[2][0]
numeros[2][1]
numeros[2][2]
```

Isso ajuda bastante a visualizar como os dois índices funcionam.

---

# Resumo

Nesta aula aprendemos:

* Arrays multidimensionais são estruturas formadas por arrays dentro de arrays.
* Um array bidimensional utiliza dois pares de colchetes:

```java
int[][]
```

* Podemos criar um array bidimensional:

```java
int[][] numeros = new int[3][3];
```

* O primeiro índice representa uma posição do array principal.
* O segundo índice representa uma posição dentro do array interno.

Exemplo:

```java
numeros[0][1]
```

* Arrays multidimensionais podem ser entendidos como uma estrutura de linhas e colunas.
* O array principal contém referências para outros arrays.
* Os arrays internos podem ter tamanhos diferentes.
* Podemos criar a primeira dimensão sem definir imediatamente as demais:

```java
int[][] numeros = new int[3][];
```

* Para percorrer duas dimensões, normalmente utilizamos dois `for`:

```java
for (int i = 0; i < numeros.length; i++) {

    for (int j = 0; j < numeros[i].length; j++) {
        System.out.println(numeros[i][j]);
    }
}
```

* O `for` externo percorre o array principal.
* O `for` interno percorre o array referenciado pela posição atual.
* O `for` interno termina completamente antes de o `for` externo avançar para a próxima posição.

---

# Estrutura mental

Guarde esta representação:

```text
int[][] numeros
       │
       ▼
   Array principal
       │
       ├──► Array 0 ──► [ ][ ][ ]
       │
       ├──► Array 1 ──► [ ][ ][ ]
       │
       └──► Array 2 ──► [ ][ ][ ]
```

E para acessar um valor:

```java
numeros[i][j]
```

```text
         i       j
         ↓       ↓
     numeros[i][j]
         │       │
         │       └── posição dentro do array interno
         └────────── posição do array principal
```

> **Dica:** ao estudar arrays multidimensionais, desenhe as referências e as posições no papel. Visualizar a estrutura facilita bastante a compreensão da lógica dos dois índices e dos `for` aninhados.

## Próxima aula

Na próxima aula, continuaremos trabalhando com arrays multidimensionais e veremos como utilizar o **`for-each`** para percorrer essa estrutura.
