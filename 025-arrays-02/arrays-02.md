# Arrays em Java — Parte 02

## Introdução

Nesta aula continuamos estudando **arrays em Java**.

Um array é utilizado para armazenar vários valores do mesmo tipo em uma única estrutura.

Por exemplo:

```java
int[] numeros = new int[3];
```

Nesse caso, estamos criando um array capaz de armazenar **3 valores do tipo `int`**.

Podemos imaginar sua estrutura da seguinte maneira:

```text
+-----+-----+-----+
|  0  |  0  |  0  |
+-----+-----+-----+
   0     1     2
```

Cada posição possui um índice, começando sempre pelo `0`.

---

# Arrays são objetos

Em Java, um array é considerado um **objeto**.

Quando fazemos:

```java
int[] numeros = new int[3];
```

temos:

```text
numeros
   |
   v
+-----+-----+-----+
|  0  |  0  |  0  |
+-----+-----+-----+
   0     1     2
```

A variável `numeros` contém uma **referência para o objeto array** criado na memória.

Isso é importante porque, em Java, praticamente sempre que trabalhamos com arrays estamos trabalhando com objetos.

---

# O tipo do array

O tipo definido no array determina o tipo de dado que cada posição poderá armazenar.

Por exemplo:

```java
int[] numeros = new int[3];
```

Todas as posições desse array são do tipo `int`.

Podemos fazer:

```java
numeros[0] = 10;
numeros[1] = 20;
numeros[2] = 30;
```

Resultado:

```text
[10, 20, 30]
```

Porém, não podemos fazer:

```java
numeros[0] = "10";
```

Isso gera um erro porque `"10"` é uma `String`, enquanto a posição `numeros[0]` espera um `int`.

Seria necessário realizar uma conversão apropriada caso quiséssemos transformar uma `String` em um número.

---

# As mesmas regras de tipos se aplicam às posições

Um array de `int` funciona como se tivéssemos várias variáveis `int` agrupadas.

Por exemplo:

```java
int[] numeros = new int[3];
```

Podemos imaginar como:

```text
int numero0;
int numero1;
int numero2;
```

Todas as posições precisam respeitar o tipo definido no array.

Portanto:

```java
numeros[0] = 100;    // válido
numeros[1] = 200;    // válido
numeros[2] = 300;    // válido
```

Mas:

```java
numeros[0] = "100";  // inválido
```

---

# Criando um array

Para criar um array, utilizamos a palavra-chave `new`.

Exemplo:

```java
int[] numeros = new int[3];
```

A expressão:

```java
new int[3]
```

cria um novo objeto array contendo três posições.

Inicialmente:

```text
[0, 0, 0]
```

---

# Valores padrão

Uma característica importante dos arrays é que suas posições são inicializadas automaticamente com um **valor padrão**.

Por exemplo:

```java
int[] numeros = new int[3];
```

As três posições recebem:

```text
0
0
0
```

Ou seja:

```text
[0, 0, 0]
```

---

## Valores padrão dos tipos primitivos

Quando um array é criado, seus elementos recebem os valores padrão correspondentes ao seu tipo.

| Tipo      | Valor padrão |
| --------- | ------------ |
| `byte`    | `0`          |
| `short`   | `0`          |
| `int`     | `0`          |
| `long`    | `0`          |
| `float`   | `0.0`        |
| `double`  | `0.0`        |
| `char`    | `'\u0000'`   |
| `boolean` | `false`      |

---

# Array de `int`

```java
int[] numeros = new int[3];
```

Resultado inicial:

```text
[0, 0, 0]
```

Podemos alterar os valores:

```java
numeros[0] = 10;
numeros[1] = 20;
numeros[2] = 30;
```

Agora:

```text
[10, 20, 30]
```

---

# Array de `double`

```java
double[] valores = new double[3];
```

Resultado inicial:

```text
[0.0, 0.0, 0.0]
```

---

# Array de `boolean`

```java
boolean[] respostas = new boolean[3];
```

Resultado inicial:

```text
[false, false, false]
```

Isso acontece porque o valor padrão de `boolean` é `false`.

---

# Array de `char`

```java
char[] letras = new char[3];
```

O valor padrão de `char` é:

```java
'\u0000'
```

Esse é o caractere nulo Unicode.

Como ele não possui uma representação visual comum, quando tentamos imprimir a posição podemos ter a impressão de que não existe nenhum conteúdo.

Por exemplo:

```java
System.out.println(letras[0]);
```

Não veremos um caractere visível sendo exibido.

---

# Arrays de tipos referência

Arrays também podem armazenar **tipos referência**.

Um exemplo muito comum é `String`.

```java
String[] nomes = new String[3];
```

Nesse caso, temos três posições capazes de armazenar referências para objetos `String`.

Como ainda não colocamos nenhum nome nas posições, o valor padrão será:

```text
[null, null, null]
```

Isso acontece porque o valor padrão dos tipos referência é:

```java
null
```

---

# Exemplo com `String`

```java
String[] nomes = new String[3];

System.out.println(nomes[0]);
System.out.println(nomes[1]);
System.out.println(nomes[2]);
```

Resultado:

```text
null
null
null
```

Podemos posteriormente preencher as posições:

```java
nomes[0] = "João";
nomes[1] = "Maria";
nomes[2] = "Pedro";
```

Agora teremos:

```text
["João", "Maria", "Pedro"]
```

---

# O que significa `null`?

Quando trabalhamos com tipos referência, `null` significa que a variável ou posição **não está apontando para nenhum objeto**.

Por exemplo:

```java
String[] nomes = new String[3];
```

Podemos representar assim:

```text
nomes
   |
   v
+--------+--------+--------+
|  null  |  null  |  null  |
+--------+--------+--------+
    0        1        2
```

Depois de atribuirmos:

```java
nomes[0] = "João";
```

teremos:

```text
+--------+--------+--------+
| "João" |  null  |  null  |
+--------+--------+--------+
    0        1        2
```

---

# Variáveis locais e valores padrão

É importante não confundir o comportamento de arrays com o de variáveis locais.

Uma variável local declarada dentro de um método não recebe automaticamente um valor padrão.

Exemplo:

```java
public static void main(String[] args) {

    int idade;

}
```

A variável `idade` foi declarada, mas não foi inicializada.

Se tentarmos fazer:

```java
public static void main(String[] args) {

    int idade;

    System.out.println(idade);
}
```

teremos um erro de compilação.

Isso ocorre porque variáveis locais precisam ser inicializadas antes de serem utilizadas.

---

# Arrays recebem valores padrão

Já no caso de um array:

```java
public static void main(String[] args) {

    int[] idades = new int[3];

    System.out.println(idades[0]);
}
```

O resultado será:

```text
0
```

Isso acontece porque os elementos do array são automaticamente inicializados com o valor padrão do tipo.

---

# Resumo dos valores padrão

Podemos guardar a seguinte tabela como referência:

```text
byte     → 0
short    → 0
int      → 0
long     → 0
float    → 0.0
double   → 0.0
char     → '\u0000'
boolean  → false
referência → null
```

Exemplos:

```java
int[] numeros = new int[3];
// [0, 0, 0]

double[] valores = new double[3];
// [0.0, 0.0, 0.0]

boolean[] respostas = new boolean[3];
// [false, false, false]

String[] nomes = new String[3];
// [null, null, null]
```

---

# Exercício de fixação

Podemos criar diferentes arrays para observar seus valores iniciais:

```java
public class Aula33 {

    public static void main(String[] args) {

        int[] numeros = new int[3];
        double[] valores = new double[3];
        boolean[] respostas = new boolean[3];
        String[] nomes = new String[3];

        System.out.println(numeros[0]);
        System.out.println(valores[0]);
        System.out.println(respostas[0]);
        System.out.println(nomes[0]);
    }
}
```

A saída será:

```text
0
0.0
false
null
```

---

# Pontos importantes

* Arrays são **objetos em Java**.
* Um array possui várias posições.
* Todas as posições possuem o mesmo tipo.
* O primeiro índice é `0`.
* O tamanho do array é definido no momento da criação.
* Utilizamos `new` para criar o objeto array.
* Os elementos recebem automaticamente valores padrão.
* Tipos numéricos recebem `0` ou `0.0`.
* `boolean` recebe `false`.
* `char` recebe `'\u0000'`.
* Tipos referência recebem `null`.
* Uma variável local comum não recebe valor padrão automaticamente.
* As posições do array podem ser alteradas individualmente.

## Exemplo final

```java
String[] nomes = new String[3];

nomes[0] = "João";
nomes[1] = "Maria";
nomes[2] = "Pedro";

System.out.println(nomes[0]);
System.out.println(nomes[1]);
System.out.println(nomes[2]);
```

Saída:

```text
João
Maria
Pedro
```

---

## Próxima aula

Na próxima aula, podemos continuar trabalhando com arrays, principalmente com **acesso às posições, índices e manipulação dos elementos**.
