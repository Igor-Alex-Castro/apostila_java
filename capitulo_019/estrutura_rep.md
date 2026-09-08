# Aula 06 — Estruturas de Repetição 01

## Laços de repetição: `while`, `do-while` e `for`

Nesta aula vamos começar a estudar as **estruturas de repetição** do Java.

As principais estruturas que vamos conhecer são:

* `while`
* `do-while`
* `for`

Essas estruturas permitem que um determinado trecho do código seja executado várias vezes.

---

# Por que utilizar estruturas de repetição?

Até agora, nossos programas eram executados basicamente de cima para baixo.

Por exemplo:

```java
System.out.println("1");
System.out.println("2");
System.out.println("3");
```

Cada instrução é executada uma vez.

Mas imagine que queremos fazer o computador contar de `1` até `10`.

Não seria interessante escrever:

```java
System.out.println(1);
System.out.println(2);
System.out.println(3);
System.out.println(4);
System.out.println(5);
System.out.println(6);
System.out.println(7);
System.out.println(8);
System.out.println(9);
System.out.println(10);
```

Podemos utilizar uma estrutura de repetição para fazer isso automaticamente.

---

# `while`

O `while` significa, basicamente:

> **Enquanto** uma determinada condição for verdadeira, execute o código.

Sua estrutura é:

```java
while (condicao) {
    // código que será repetido
}
```

Assim como acontece com o `if`, a condição do `while` precisa resultar em um valor booleano:

```text
true
```

ou:

```text
false
```

---

# Primeiro exemplo

Vamos criar uma variável para funcionar como contador:

```java
int counter = 0;
```

Agora queremos imprimir os valores enquanto o contador for menor que `10`:

```java
while (counter < 10) {
    System.out.println(counter);
}
```

Porém, temos um problema.

O valor de `counter` nunca é alterado.

Ele começa com:

```text
0
```

A condição:

```java
counter < 10
```

será:

```text
0 < 10 → true
```

Então o código será executado.

Depois o Java volta para o `while` e verifica novamente:

```text
0 < 10 → true
```

E executa novamente.

Isso continuará acontecendo indefinidamente.

O programa ficará imprimindo:

```text
0
0
0
0
0
0
...
```

até que o programa seja interrompido.

---

# Evitando o loop infinito

Sempre que utilizamos um laço de repetição, precisamos tomar cuidado para que a condição seja alterada em algum momento.

Podemos incrementar o contador:

```java
int counter = 0;

while (counter < 10) {
    System.out.println(counter);
    counter = counter + 1;
}
```

Também podemos escrever:

```java
counter++;
```

Então:

```java
int counter = 0;

while (counter < 10) {
    System.out.println(counter);
    counter++;
}
```

Agora o contador será alterado a cada execução.

---

# Como o `while` funciona?

Inicialmente:

```text
counter = 0
```

O Java verifica:

```text
0 < 10 → true
```

Imprime:

```text
0
```

Depois:

```text
counter++
```

O contador passa a ser:

```text
1
```

O Java verifica novamente:

```text
1 < 10 → true
```

Imprime:

```text
1
```

E assim sucessivamente:

```text
0
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

Quando o contador chegar a:

```text
10
```

teremos:

```text
10 < 10 → false
```

Nesse momento, o `while` é encerrado.

---

# Contando de 0 até 9

O código:

```java
int counter = 0;

while (counter < 10) {
    System.out.println(counter);
    counter++;
}
```

produz:

```text
0
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

Observe que o `10` não é impresso.

Isso acontece porque a condição é:

```java
counter < 10
```

Quando `counter` vale `10`, a condição passa a ser falsa.

---

# Contando de 1 até 10

Se quisermos começar em `1`, podemos alterar o valor inicial:

```java
int counter = 1;

while (counter <= 10) {
    System.out.println(counter);
    counter++;
}
```

Resultado:

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
10
```

Outra possibilidade é alterar a condição:

```java
int counter = 0;

while (counter < 10) {
    counter++;
    System.out.println(counter);
}
```

Nesse caso, incrementamos antes de imprimir.

---

# Incrementando de outras formas

Também podemos alterar o contador de outras maneiras.

Por exemplo:

```java
counter = counter + 1;
```

ou:

```java
counter++;
```

As duas formas incrementam o valor em `1`.

Também podemos incrementar de outros valores.

Por exemplo:

```java
counter = counter + 5;
```

Nesse caso:

```java
int counter = 0;

while (counter < 10) {
    System.out.println(counter);
    counter += 5;
}
```

Teremos:

```text
0
5
```

Depois o contador será `10`, a condição será falsa e o laço terminará.

---

# Cuidado com loops infinitos

Um dos principais cuidados ao utilizar o `while` é garantir que a condição possa se tornar falsa.

Por exemplo:

```java
int counter = 0;

while (counter < 10) {
    System.out.println(counter);
}
```

Esse código possui um **loop infinito**, porque `counter` nunca é alterado.

Portanto, sempre verifique se existe alguma alteração na variável utilizada na condição.

---

# Quando a condição já começa como `false`

Também é importante saber que o `while` pode não executar nenhuma vez.

Por exemplo:

```java
int counter = 12;

while (counter < 10) {
    System.out.println(counter);
}
```

A condição será:

```text
12 < 10 → false
```

Como a condição já começa sendo falsa, o código dentro do `while` não será executado.

Isso é semelhante ao comportamento do `if`.

---

# `do-while`

A segunda estrutura que vamos conhecer é o `do-while`.

A diferença principal entre `while` e `do-while` é:

* `while` verifica a condição **antes** de executar.
* `do-while` executa o código **pelo menos uma vez** antes de verificar a condição.

A estrutura é:

```java
do {
    // código
} while (condicao);
```

---

# Exemplo com `do-while`

Vamos utilizar:

```java
int counter = 12;
```

E:

```java
do {
    System.out.println(counter);
} while (counter < 10);
```

Primeiro o Java executa:

```java
System.out.println(counter);
```

Então imprime:

```text
12
```

Somente depois disso ele verifica:

```text
12 < 10 → false
```

Como a condição é falsa, o laço termina.

Mesmo assim, o código foi executado **uma vez**.

---

# Diferença entre `while` e `do-while`

### `while`

```java
while (condicao) {
    // código
}
```

A condição é verificada primeiro.

Se for falsa desde o início:

```text
false
```

o código não será executado nenhuma vez.

---

### `do-while`

```java
do {
    // código
} while (condicao);
```

O código é executado primeiro.

Depois a condição é verificada.

Por isso, o código será executado **pelo menos uma vez**.

---

# Comparando os dois

## `while`

```java
int counter = 12;

while (counter < 10) {
    System.out.println(counter);
}
```

Resultado:

```text
Nenhuma saída
```

Porque:

```text
12 < 10 → false
```

---

## `do-while`

```java
int counter = 12;

do {
    System.out.println(counter);
} while (counter < 10);
```

Resultado:

```text
12
```

Porque o código é executado uma vez antes da verificação.

---

# Alterando o contador no `do-while`

Assim como no `while`, também precisamos tomar cuidado para não criar um loop infinito.

Por exemplo:

```java
int counter = 0;

do {
    System.out.println(counter);
    counter++;
} while (counter < 10);
```

Resultado:

```text
0
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

O contador é incrementado a cada execução e, quando chega a `10`, a condição se torna falsa.

---

# `for`

A terceira estrutura de repetição que vamos conhecer é o `for`.

O `for` é muito utilizado quando sabemos que queremos realizar uma repetição baseada em um contador ou índice.

A estrutura básica é:

```java
for (inicialização; condição; incremento) {
    // código
}
```

O `for` possui três partes principais:

```text
1. Inicialização
2. Condição
3. Incremento
```

---

# Estrutura do `for`

Podemos escrever:

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

Vamos entender cada parte.

### 1. Inicialização

```java
int i = 0;
```

Aqui declaramos e inicializamos a variável.

Ela começa com:

```text
0
```

### 2. Condição

```java
i < 10
```

Essa condição determina até quando o laço continuará sendo executado.

### 3. Incremento

```java
i++
```

A cada repetição, o valor de `i` será incrementado em `1`.

---

# Exemplo completo

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

Resultado:

```text
0
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

# Entendendo a execução do `for`

Podemos imaginar o processo da seguinte maneira:

```text
int i = 0
     ↓
i < 10?
     ↓
  true
     ↓
executa o código
     ↓
i++
     ↓
i < 10?
     ↓
  true
     ↓
executa o código
     ↓
i++
     ↓
...
     ↓
i < 10?
     ↓
 false
     ↓
fim do for
```

---

# O que é executado uma vez e o que é executado várias vezes?

No `for`:

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

A inicialização:

```java
int i = 0
```

é executada **uma única vez**.

A condição:

```java
i < 10
```

é verificada a cada repetição.

O incremento:

```java
i++
```

é executado após cada execução do corpo do `for`.

O código dentro das chaves:

```java
System.out.println(i);
```

é executado várias vezes.

---

# Variável declarada dentro do `for`

É muito comum declararmos a variável de controle diretamente dentro do `for`:

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

Nesse caso, `i` é uma variável local ao `for`.

Ela pode ser utilizada dentro do escopo do laço.

Por exemplo:

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

Após o término do `for`, essa variável não estará disponível fora do seu escopo.

---

# Podemos declarar a variável antes

Também podemos declarar a variável antes do `for`:

```java
int i = 0;

for (; i < 10; i++) {
    System.out.println(i);
}
```

Nesse caso, a inicialização não está dentro do `for`, porque ela já foi feita anteriormente.

É necessário apenas colocar o primeiro ponto e vírgula:

```java
for (; i < 10; i++) {
}
```

Porém, é muito comum encontrar a variável sendo declarada diretamente no `for`:

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

---

# Utilizando `j` em outro `for`

Quando temos mais de um laço, é comum encontrar variáveis chamadas:

```java
i
```

e:

```java
j
```

Por exemplo:

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

E em outro laço:

```java
for (int j = 0; j < 10; j++) {
    System.out.println(j);
}
```

Não existe um significado especial para `i` ou `j`.

São apenas nomes muito utilizados por convenção para representar índices e contadores.

---

# `while` x `do-while` x `for`

Podemos resumir as três estruturas:

| Estrutura  | Característica                                                     |
| ---------- | ------------------------------------------------------------------ |
| `while`    | Verifica a condição antes de executar                              |
| `do-while` | Executa pelo menos uma vez antes de verificar                      |
| `for`      | Muito utilizado para repetições controladas por contador ou índice |

### `while`

```java
while (condicao) {
    // código
}
```

### `do-while`

```java
do {
    // código
} while (condicao);
```

### `for`

```java
for (inicializacao; condicao; incremento) {
    // código
}
```

---

# Resumo

Nesta aula aprendemos que as estruturas de repetição permitem executar um determinado trecho de código várias vezes.

## `while`

Executa enquanto uma condição for verdadeira:

```java
while (counter < 10) {
    System.out.println(counter);
    counter++;
}
```

A condição é verificada antes da execução.

---

## `do-while`

Executa o bloco pelo menos uma vez:

```java
do {
    System.out.println(counter);
    counter++;
} while (counter < 10);
```

A condição é verificada depois da execução.

---

## `for`

Possui três partes:

```java
for (inicializacao; condicao; incremento) {
    // código
}
```

Exemplo:

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

---

# Pontos importantes

* Estruturas de repetição permitem repetir código.
* A condição do `while` precisa resultar em `boolean`.
* O `while` pode executar **zero ou mais vezes**.
* O `do-while` executa **uma ou mais vezes**.
* O `for` é muito utilizado para contagens e índices.
* É importante alterar a variável utilizada na condição para evitar loops infinitos.
* A variável declarada dentro do `for` possui escopo local ao laço.

---

# Conclusão

Nesta aula começamos a estudar as **estruturas de repetição do Java**.

Aprendemos:

```text
while
do-while
for
```

Essas estruturas são fundamentais para fazer um programa repetir determinadas operações sem precisar escrever o mesmo código várias vezes.

Nas próximas aulas podemos aprofundar ainda mais o uso dos laços de repetição.

Até a próxima! 🚀
