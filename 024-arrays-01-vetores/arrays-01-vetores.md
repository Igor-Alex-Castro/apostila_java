# Aula 07 — Arrays (Vetores)

## Introdução

Depois de estudarmos as estruturas de repetição, vamos começar a trabalhar diretamente com **Arrays (vetores)**.

Arrays são mais simples do que parecem, principalmente quando conseguimos visualizar o que está acontecendo na memória.

---

# 1. O problema

Imagine que temos o seguinte problema:

> Precisamos guardar **três idades de pessoas**.

Da forma que conhecemos até agora, poderíamos fazer:

```java
int idade1 = 20;
int idade2 = 15;
int idade3 = 11;
```

O problema é que, se precisarmos trabalhar com várias idades, teremos que criar várias variáveis:

```java
int idade1;
int idade2;
int idade3;
int idade4;
int idade5;
// ...
```

E, para imprimir todas elas, também precisaríamos fazer algo parecido:

```java
System.out.println(idade1);
System.out.println(idade2);
System.out.println(idade3);
```

Quanto maior a quantidade de valores, mais complicado fica trabalhar dessa maneira.

---

# 2. O que são Arrays?

Quando temos vários valores que pertencem ao **mesmo tipo** e estão relacionados ao mesmo grupo, podemos utilizar um **Array**.

Por exemplo:

* Idades;
* Nomes;
* Salários;
* Notas;
* Produtos;
* Outros valores do mesmo tipo.

Um Array permite armazenar **vários valores dentro de uma única variável**.

---

# 3. Array como referência

Anteriormente, trabalhávamos com uma variável primitiva:

```java
int idade = 20;
```

Podemos imaginar essa variável como uma referência para um espaço na memória onde o valor `20` está armazenado.

Com um Array, temos uma estrutura capaz de armazenar vários valores.

Podemos imaginar:

```text
idades
   |
   v
+-----+-----+-----+
|  20 |  15 |  11 |
+-----+-----+-----+
```

Nesse caso, a variável `idades` faz referência a um objeto na memória que possui várias posições.

---

# 4. Declarando um Array

Para declarar um Array de inteiros, podemos fazer:

```java
int[] idades;
```

A sintaxe é:

```java
tipo[] nomeDaVariavel;
```

Por exemplo:

```java
int[] idades;
```

Isso significa:

> A variável `idades` é uma variável de referência para um Array de inteiros.

---

# 5. Array é uma variável de referência

É importante entender que:

```java
int[] idades;
```

não é um tipo primitivo.

Temos aqui uma **variável de referência**.

Podemos representar:

```text
idades
   |
   v
Objeto Array
```

Enquanto:

```java
int idade = 20;
```

utiliza o tipo primitivo `int`.

---

# 6. Duas formas de declarar

O Java permite declarar o Array de duas formas:

```java
int[] idades;
```

ou:

```java
int idades[];
```

As duas formas possuem o mesmo significado.

Porém, é recomendado utilizar:

```java
int[] idades;
```

Dessa maneira, ao olhar para a declaração, fica mais evidente que estamos trabalhando com um Array de inteiros.

---

# 7. Inicializando com `null`

Como o Array é uma variável de referência, podemos inicializá-lo com:

```java
int[] idades = null;
```

`null` significa que a variável **não está fazendo referência a nenhum objeto**.

Podemos visualizar assim:

```text
idades
   |
   v
 null
```

Nesse momento, ainda não temos um Array criado na memória.

---

# 8. Criando o Array

Agora precisamos criar o objeto Array.

Para isso, utilizamos o operador `new`:

```java
int[] idades = new int[3];
```

Essa declaração significa:

> Crie um Array de inteiros com **3 posições**.

Podemos visualizar:

```text
idades
   |
   v
+-----+-----+-----+
|     |     |     |
+-----+-----+-----+
   0     1     2
```

Temos três espaços na memória.

---

# 9. Tamanho do Array

Ao criar um Array, precisamos informar a quantidade de posições que ele terá.

Por exemplo:

```java
new int[3]
```

cria três posições.

```java
new int[5]
```

cria cinco posições.

```java
new int[10]
```

cria dez posições.

Depois que o Array é criado, seu tamanho não pode ser alterado.

---

# 10. Arrays são indexados

Uma característica importante dos Arrays é que suas posições são identificadas por **índices**.

O índice começa sempre em `0`.

Se temos um Array com três posições:

```java
int[] idades = new int[3];
```

teremos:

```text
Índice:

+-----+-----+-----+
|     |     |     |
+-----+-----+-----+
   0     1     2
```

Temos **3 posições**, mas o último índice é `2`.

Isso acontece porque a contagem começa em `0`.

---

# 11. Acessando uma posição

Para acessar uma posição específica, utilizamos os colchetes:

```java
idades[0]
```

Isso significa:

> Acesse a posição `0` do Array `idades`.

Por exemplo:

```java
System.out.println(idades[0]);
```

---

# 12. Valores padrão

Quando criamos um Array de tipos primitivos, suas posições são inicializadas automaticamente com valores padrão.

Para tipos numéricos inteiros, como `int`, o valor padrão é:

```text
0
```

Portanto:

```java
int[] idades = new int[3];

System.out.println(idades[0]);
System.out.println(idades[1]);
System.out.println(idades[2]);
```

Teremos:

```text
0
0
0
```

Isso acontece porque as três posições foram inicializadas com o valor padrão do tipo `int`.

---

# 13. Valores padrão em Arrays

De forma geral:

| Tipo                                         | Valor padrão |
| -------------------------------------------- | ------------ |
| Tipos inteiros (`int`, `long`, etc.)         | `0`          |
| Tipos de ponto flutuante (`float`, `double`) | `0.0`        |
| `boolean`                                    | `false`      |
| Tipos de referência, como `String`           | `null`       |

---

# 14. Atribuindo valores

Podemos atribuir valores diretamente às posições do Array.

Por exemplo:

```java
int[] idades = new int[3];

idades[0] = 21;
idades[1] = 15;
idades[2] = 11;
```

Agora temos:

```text
+-----+-----+-----+
|  21 |  15 |  11 |
+-----+-----+-----+
   0     1     2
```

Podemos imprimir os valores:

```java
System.out.println(idades[0]);
System.out.println(idades[1]);
System.out.println(idades[2]);
```

Resultado:

```text
21
15
11
```

---

# 15. Acessando uma posição que não existe

Precisamos tomar cuidado para não tentar acessar uma posição que não existe.

Nosso Array possui:

```java
int[] idades = new int[3];
```

Portanto, seus índices são:

```text
0
1
2
```

Não existe a posição:

```java
idades[3]
```

Se tentarmos acessar:

```java
System.out.println(idades[3]);
```

teremos uma exceção durante a execução do programa:

```text
ArrayIndexOutOfBoundsException
```

Isso acontece porque estamos tentando acessar um índice que está fora dos limites do Array.

---

# 16. Regra importante sobre índices

Se um Array possui `N` posições:

```text
Primeiro índice = 0
Último índice = N - 1
```

Por exemplo:

```java
int[] idades = new int[3];
```

Possui:

```text
3 posições
```

Mas os índices são:

```text
0 até 2
```

Outro exemplo:

```java
int[] numeros = new int[10];
```

Possui:

```text
10 posições
```

E os índices vão de:

```text
0 até 9
```

---

# 17. Resumo visual

Podemos representar um Array da seguinte maneira:

```text
int[] idades = new int[3];

idades
   |
   v
+-----+-----+-----+
|  21 |  15 |  11 |
+-----+-----+-----+
   0     1     2
```

A variável:

```java
idades
```

faz referência ao objeto Array.

O objeto possui três posições:

```text
0
1
2
```

E cada posição armazena um valor `int`.

---

# 18. Código completo

```java
public class Aula07Arrays {

    public static void main(String[] args) {

        int[] idades = new int[3];

        idades[0] = 21;
        idades[1] = 15;
        idades[2] = 11;

        System.out.println(idades[0]);
        System.out.println(idades[1]);
        System.out.println(idades[2]);
    }
}
```

Resultado:

```text
21
15
11
```

---

# Resumo da aula

Nesta aula tivemos uma introdução aos **Arrays (vetores)**.

Os principais conceitos são:

* Arrays permitem armazenar vários valores relacionados em uma única variável.
* Os valores precisam ser compatíveis com o tipo do Array.
* Arrays são objetos na memória.
* A variável que referencia o Array é uma variável de referência.
* Arrays são declarados utilizando `[]`.
* O tamanho do Array é definido no momento da criação.
* Os índices começam em `0`.
* Um Array com `3` posições possui os índices `0`, `1` e `2`.
* Arrays de tipos primitivos recebem valores padrão.
* Um Array de `int` recebe `0` como valor inicial em suas posições.
* Tipos de referência recebem `null` como valor inicial.
* Não podemos acessar uma posição que não existe.
* A tentativa de acessar um índice inválido gera uma `ArrayIndexOutOfBoundsException`.

### Sintaxe básica

Declaração:

```java
int[] idades;
```

Criação:

```java
idades = new int[3];
```

Declaração e criação juntas:

```java
int[] idades = new int[3];
```

Atribuição:

```java
idades[0] = 21;
```

Acesso:

```java
System.out.println(idades[0]);
```

---

## Conceito principal

Um Array pode ser entendido como uma **estrutura com várias posições de um mesmo tipo**, acessadas através de índices.

```text
Array
  ↓
+-----+-----+-----+
|     |     |     |
+-----+-----+-----+
   0     1     2
```

A principal regra para lembrar é:

> **Arrays começam seus índices em `0` e terminam em `tamanho - 1`.**
