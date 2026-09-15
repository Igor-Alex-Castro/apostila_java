# Arrays em Java — Parte 04 — For-Each

## Introdução

Nesta aula vamos continuar estudando arrays e aprender uma nova forma de percorrer seus elementos.

Até agora utilizamos o `for` tradicional, também conhecido como **for indexado**, para acessar cada posição do array.

Agora conheceremos o **for-each**, uma forma mais simples de percorrer todos os elementos de um array quando não precisamos trabalhar diretamente com os índices.

Também veremos uma outra forma de **inicializar arrays diretamente com seus valores**.

---

# Inicializando um array diretamente

Até agora aprendemos que podemos criar um array informando seu tamanho:

```java
int[] numeros = new int[5];
```

Nesse caso, estamos criando um array com cinco posições:

```text
[0, 0, 0, 0, 0]
```

Depois poderíamos preencher cada posição:

```java
numeros[0] = 1;
numeros[1] = 2;
numeros[2] = 3;
numeros[3] = 4;
numeros[4] = 5;
```

Porém, existe uma forma mais simples de fazer isso.

---

# Inicialização com valores

Podemos criar o array e informar seus valores diretamente:

```java
int[] numeros = {1, 2, 3, 4, 5};
```

Nesse caso, o Java calcula automaticamente o tamanho do array.

Temos:

```text
[1, 2, 3, 4, 5]
```

E o tamanho será:

```java
numeros.length
```

Resultado:

```text
5
```

---

# Como o Java calcula o tamanho?

Quando escrevemos:

```java
int[] numeros = {1, 2, 3, 4, 5};
```

não precisamos informar:

```java
new int[5]
```

O Java conta a quantidade de valores que foram informados.

Temos cinco valores:

```text
1
2
3
4
5
```

Portanto, o array terá cinco posições.

Os índices serão:

```text
Valor:   1   2   3   4   5
Índice:  0   1   2   3   4
```

---

# Utilizando `new`

Também podemos utilizar a palavra-chave `new` juntamente com os valores:

```java
int[] numeros = new int[]{1, 2, 3, 4, 5};
```

Essa forma também cria um array com cinco posições.

Na prática:

```java
int[] numeros = {1, 2, 3, 4, 5};
```

e:

```java
int[] numeros = new int[]{1, 2, 3, 4, 5};
```

produzem um array equivalente.

A primeira forma é mais simples e comum quando estamos declarando e inicializando o array ao mesmo tempo.

---

# Não podemos informar o tamanho junto com os valores

Quando informamos diretamente os valores, não precisamos e não devemos informar o tamanho separadamente.

Por exemplo:

```java
int[] numeros = new int[5]{1, 2, 3, 4, 5};
```

Essa sintaxe é inválida.

O Java já consegue descobrir o tamanho contando os elementos:

```java
int[] numeros = {1, 2, 3, 4, 5};
```

Portanto, não precisamos escrever o `5`.

---

# O tamanho é calculado automaticamente

Se fizermos:

```java
int[] numeros = {1, 2, 3};
```

teremos:

```text
Tamanho: 3

Índices:
0
1
2
```

Se alterarmos para:

```java
int[] numeros = {1, 2, 3, 4, 5};
```

teremos:

```text
Tamanho: 5

Índices:
0
1
2
3
4
```

O tamanho sempre será calculado com base na quantidade de elementos fornecidos.

---

# Percorrendo o array com `for`

Podemos utilizar o `for` tradicional para imprimir os valores:

```java
int[] numeros = {1, 2, 3, 4, 5};

for (int i = 0; i < numeros.length; i++) {
    System.out.println(numeros[i]);
}
```

Resultado:

```text
1
2
3
4
5
```

Nesse caso, utilizamos o índice `i` para acessar cada posição:

```text
i = 0 → numeros[0]
i = 1 → numeros[1]
i = 2 → numeros[2]
i = 3 → numeros[3]
i = 4 → numeros[4]
```

---

# For-each

Existe uma maneira mais simples de percorrer os elementos quando não precisamos do índice.

Essa estrutura é chamada de **for-each**.

A sintaxe básica é:

```java
for (Tipo variavel : array) {
    // código
}
```

Por exemplo:

```java
int[] numeros = {1, 2, 3, 4, 5};

for (int num : numeros) {
    System.out.println(num);
}
```

Resultado:

```text
1
2
3
4
5
```

---

# Entendendo a estrutura do for-each

Observe:

```java
for (int num : numeros)
```

Temos três partes importantes:

### `int`

É o tipo dos elementos do array.

Como o array foi declarado como:

```java
int[] numeros
```

cada elemento é do tipo `int`.

### `num`

É uma **variável local** que receberá cada elemento do array durante a iteração.

### `numeros`

É o array que queremos percorrer.

Podemos interpretar:

```java
for (int num : numeros)
```

como:

> Para cada elemento do array `numeros`, coloque esse elemento na variável `num`.

---

# Exemplo passo a passo

Considere:

```java
int[] numeros = {1, 2, 3, 4, 5};

for (int num : numeros) {
    System.out.println(num);
}
```

Na primeira iteração:

```text
num → 1
```

Depois:

```text
num → 2
```

Depois:

```text
num → 3
```

Depois:

```text
num → 4
```

E finalmente:

```text
num → 5
```

A cada iteração, a variável `num` recebe o próximo elemento do array.

---

# A variável do for-each é local

A variável declarada no `for-each`:

```java
for (int num : numeros) {
    System.out.println(num);
}
```

é uma variável local.

Ela existe dentro do escopo do `for`.

Depois que o `for` termina, essa variável deixa de existir naquele escopo.

Por exemplo:

```java
for (int num : numeros) {
    System.out.println(num);
}
```

Aqui `num` pode ser utilizado normalmente.

Mas fora do `for`:

```java
System.out.println(num);
```

não será possível utilizá-lo, porque a variável não existe mais nesse escopo.

---

# O tipo da variável deve ser compatível

O tipo da variável utilizada no `for-each` deve ser compatível com o tipo dos elementos do array.

Se temos:

```java
int[] numeros = {1, 2, 3, 4, 5};
```

podemos utilizar:

```java
for (int num : numeros) {
    System.out.println(num);
}
```

Mas não podemos simplesmente fazer:

```java
for (String num : numeros) {
    System.out.println(num);
}
```

Isso não funcionará porque os elementos do array são `int`, e não `String`.

---

# Exemplo com `String`

Se o array for:

```java
String[] nomes = {"Maria", "João", "Pedro"};
```

podemos utilizar:

```java
for (String nome : nomes) {
    System.out.println(nome);
}
```

Resultado:

```text
Maria
João
Pedro
```

Observe que o tipo da variável é `String`, porque os elementos do array também são `String`.

---

# For tradicional x For-each

Podemos comparar as duas formas.

## For tradicional

```java
int[] numeros = {1, 2, 3, 4, 5};

for (int i = 0; i < numeros.length; i++) {
    System.out.println(numeros[i]);
}
```

Aqui trabalhamos diretamente com o índice.

Temos:

```text
i = 0 → numeros[0]
i = 1 → numeros[1]
i = 2 → numeros[2]
i = 3 → numeros[3]
i = 4 → numeros[4]
```

---

## For-each

```java
int[] numeros = {1, 2, 3, 4, 5};

for (int num : numeros) {
    System.out.println(num);
}
```

Aqui não precisamos controlar o índice.

O Java percorre os elementos automaticamente.

---

# Quando utilizar cada um?

## For tradicional

É indicado quando precisamos do **índice**.

Por exemplo:

```java
for (int i = 0; i < numeros.length; i++) {
    System.out.println("Índice: " + i);
    System.out.println("Valor: " + numeros[i]);
}
```

Resultado:

```text
Índice: 0
Valor: 1

Índice: 1
Valor: 2

Índice: 2
Valor: 3
```

---

## For-each

É indicado quando queremos simplesmente percorrer os elementos.

Por exemplo:

```java
for (int num : numeros) {
    System.out.println(num);
}
```

Nesse caso, não precisamos saber qual é o índice.

---

# O que acontece por baixo dos panos?

O `for-each` é uma forma simplificada de percorrer os elementos.

Quando escrevemos:

```java
for (int num : numeros) {
    System.out.println(num);
}
```

podemos imaginar que o Java está realizando, conceitualmente, o trabalho de percorrer cada posição do array.

De forma simplificada:

```text
Primeira iteração:
num → numeros[0]

Segunda iteração:
num → numeros[1]

Terceira iteração:
num → numeros[2]

...
```

Isso acontece automaticamente.

Não precisamos escrever manualmente:

```java
int i = 0;
i < numeros.length;
i++;
```

O `for-each` cuida dessa lógica para nós.

---

# Limitação do for-each

Uma característica importante é que o `for-each` **não fornece diretamente o índice**.

Por exemplo:

```java
for (int num : numeros) {
    System.out.println(num);
}
```

Temos acesso ao valor:

```text
1
2
3
4
5
```

Mas não temos diretamente:

```text
0
1
2
3
4
```

Se precisarmos saber ou manipular o índice, o `for` tradicional geralmente é mais adequado.

---

# Exemplo completo

```java
public class Aula35 {

    public static void main(String[] args) {

        int[] numeros = {1, 2, 3, 4, 5};

        for (int num : numeros) {
            System.out.println(num);
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
```

---

# Outro exemplo com nomes

```java
public class Aula35 {

    public static void main(String[] args) {

        String[] nomes = {
            "Maria",
            "João",
            "Pedro"
        };

        for (String nome : nomes) {
            System.out.println(nome);
        }
    }
}
```

Saída:

```text
Maria
João
Pedro
```

---

# Resumo

Nesta aula aprendemos:

* Podemos inicializar um array diretamente com seus valores.
* O Java calcula automaticamente o tamanho quando utilizamos essa sintaxe.
* Podemos escrever:

```java
int[] numeros = {1, 2, 3, 4, 5};
```

* Também podemos utilizar:

```java
int[] numeros = new int[]{1, 2, 3, 4, 5};
```

* O `for-each` permite percorrer os elementos de um array de forma simplificada.
* A sintaxe básica é:

```java
for (Tipo variavel : array) {
    // código
}
```

* A variável criada dentro do `for-each` é uma variável local.
* O tipo da variável deve ser compatível com o tipo dos elementos do array.
* O `for-each` percorre automaticamente todos os elementos.
* O `for-each` não fornece diretamente o índice.
* Quando precisamos do índice, o `for` tradicional é mais adequado.

---

# Comparação rápida

| Característica             | `for` tradicional | `for-each`   |
| -------------------------- | ----------------- | ------------ |
| Percorrer array            | Sim               | Sim          |
| Acessar valor              | Sim               | Sim          |
| Acessar índice diretamente | Sim               | Não          |
| Precisa controlar `i`      | Sim               | Não          |
| Precisa usar `length`      | Normalmente sim   | Não          |
| Sintaxe                    | Mais detalhada    | Mais simples |

## Regra prática

Use o **`for-each`** quando você só precisa dos valores:

```java
for (int num : numeros) {
    System.out.println(num);
}
```

Use o **`for` tradicional** quando precisar do índice:

```java
for (int i = 0; i < numeros.length; i++) {
    System.out.println(numeros[i]);
}
```

> **Próxima aula:** continuidade dos estudos sobre arrays e outras formas de trabalhar com seus elementos.
