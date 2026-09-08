# Aula 06 — Estruturas de Repetição 02

## Exercício com `for`

Nesta aula vamos fazer um pequeno exercício para praticar as **estruturas de repetição**, utilizando principalmente o `for`.

O exercício proposto é:

> **Imprima todos os números pares de 1 até 1 milhão.**

---

# Resolução

Existem várias formas de resolver esse problema.

Podemos utilizar qualquer uma das estruturas de repetição que aprendemos e, mesmo dentro de uma mesma estrutura, existem diferentes maneiras de chegar ao resultado.

Uma possibilidade é utilizar o `for`.

---

## Solução 1 — Contando de 2 em 2

Como queremos somente os números pares, podemos começar diretamente no número `2` e incrementar o contador de `2` em `2`.

```java
for (int i = 2; i <= 1000000; i += 2) {
    System.out.println(i);
}
```

O resultado será:

```text
2
4
6
8
10
12
14
...
999998
1000000
```

Como começamos em `2` e sempre adicionamos `2`, todos os valores impressos serão pares.

---

# Entendendo o `for`

O código:

```java
for (int i = 2; i <= 1000000; i += 2) {
    System.out.println(i);
}
```

possui três partes:

### Inicialização

```java
int i = 2;
```

O contador começa em `2`.

### Condição

```java
i <= 1000000;
```

O `for` continuará enquanto `i` for menor ou igual a `1.000.000`.

### Incremento

```java
i += 2;
```

A cada repetição, adicionamos `2` ao contador.

Assim:

```text
2 → 4 → 6 → 8 → 10 → 12 → ...
```

---

# Um problema com essa solução

Embora essa solução resolva o exercício atual, precisamos pensar em algo muito importante no desenvolvimento de software:

> **Os requisitos podem mudar.**

Imagine que inicialmente o requisito seja:

> "Imprima todos os números pares de 1 até 1 milhão."

Nossa solução funciona perfeitamente:

```java
for (int i = 2; i <= 1000000; i += 2) {
    System.out.println(i);
}
```

Mas imagine que o requisito seja alterado para:

> "Agora comece de 1 e continue até 1 milhão."

Se simplesmente alterarmos:

```java
int i = 1;
```

teremos:

```java
for (int i = 1; i <= 1000000; i += 2) {
    System.out.println(i);
}
```

O resultado será:

```text
1
3
5
7
9
11
13
...
```

Ou seja, passaremos a imprimir os **números ímpares**.

---

# Solução 2 — Verificando se o número é par

Uma alternativa mais flexível é percorrer todos os números e verificar se cada um deles é par.

Para descobrir se um número é par, podemos utilizar o operador `%`, que retorna o resto de uma divisão.

Por exemplo:

```java
4 % 2
```

Resultado:

```text
0
```

Já:

```java
5 % 2
```

Resultado:

```text
1
```

Portanto, podemos verificar:

```java
if (i % 2 == 0) {
    System.out.println(i);
}
```

Se o resto da divisão por `2` for `0`, significa que o número é par.

---

## Código completo

```java
for (int i = 1; i <= 1000000; i++) {
    if (i % 2 == 0) {
        System.out.println(i);
    }
}
```

Nesse caso, começamos em `1` e percorremos todos os números até `1.000.000`.

Para cada número, verificamos:

```java
i % 2 == 0
```

Se for verdadeiro, imprimimos o número.

---

# Como identificar um número par?

A regra utilizada é:

```java
numero % 2 == 0
```

Se o resultado for `0`, o número é par.

Exemplos:

```text
2 % 2 = 0 → par
4 % 2 = 0 → par
6 % 2 = 0 → par
8 % 2 = 0 → par
10 % 2 = 0 → par
```

Para números ímpares:

```text
1 % 2 = 1 → ímpar
3 % 2 = 1 → ímpar
5 % 2 = 1 → ímpar
7 % 2 = 1 → ímpar
9 % 2 = 1 → ímpar
```

Por isso utilizamos:

```java
if (i % 2 == 0)
```

---

# Comparando as duas soluções

## Solução 1

```java
for (int i = 2; i <= 1000000; i += 2) {
    System.out.println(i);
}
```

### Vantagem

É mais simples e eficiente para o requisito específico de imprimir números pares, porque percorremos somente os números pares.

### Desvantagem

A lógica está mais diretamente ligada ao requisito atual.

Se o ponto inicial ou a regra do problema mudar, talvez seja necessário alterar a lógica do `for`.

---

## Solução 2

```java
for (int i = 1; i <= 1000000; i++) {
    if (i % 2 == 0) {
        System.out.println(i);
    }
}
```

### Vantagem

A regra de negócio fica explícita:

```java
i % 2 == 0
```

Estamos dizendo claramente:

> "Se o número for par, imprima."

Isso facilita uma eventual alteração do problema.

Por exemplo, podemos começar em `1` sem alterar a lógica de identificação dos números pares.

---

# Pensando nas mudanças de requisitos

Esse exercício é simples, mas traz uma lição importante sobre desenvolvimento de software.

Não devemos pensar somente no problema que estamos resolvendo **agora**.

Também precisamos pensar:

> "O que pode mudar no futuro?"

Imagine que amanhã alguém diga:

* Comece em `1`.
* Termine em `500`.
* Agora imprima os números ímpares.
* Agora imprima somente números divisíveis por `3`.
* Agora permita que o limite seja configurado pelo usuário.

Os requisitos podem mudar.

Por isso, é importante escrever um código que seja fácil de entender e modificar.

---

# Regras de negócio mudam

No desenvolvimento de software, é muito comum receber novas funcionalidades ou alterações nas regras existentes.

Uma aplicação que funciona perfeitamente hoje pode precisar ser modificada amanhã porque uma regra de negócio mudou.

Por isso, não devemos pensar somente:

> "Meu código funciona."

Também precisamos pensar:

> "Meu código será fácil de alterar quando o requisito mudar?"

Essa preocupação faz parte da manutenção e evolução de um sistema.

---

# Exemplo final

Uma solução utilizando o `for` e verificando se o número é par:

```java
public class Aula06EstruturasRepeticao02 {

    public static void main(String[] args) {

        for (int i = 1; i <= 1000000; i++) {

            if (i % 2 == 0) {
                System.out.println(i);
            }

        }
    }
}
```

---

# Resumo

Neste exercício praticamos o uso do `for` para trabalhar com números.

Aprendemos duas maneiras de encontrar números pares.

### Contando de 2 em 2

```java
for (int i = 2; i <= 1000000; i += 2) {
    System.out.println(i);
}
```

### Verificando se o número é par

```java
for (int i = 1; i <= 1000000; i++) {
    if (i % 2 == 0) {
        System.out.println(i);
    }
}
```

A segunda solução utiliza:

```java
i % 2 == 0
```

para verificar se o número é par.

---

# O mais importante do exercício

Além de aprender a utilizar o `for`, o exercício mostra uma preocupação muito importante no desenvolvimento de software:

> **Os requisitos podem mudar.**

Por isso, ao desenvolver uma solução, devemos pensar não apenas no problema atual, mas também em como o código poderá ser alterado no futuro.

Na prática, grande parte do trabalho de desenvolvimento envolve:

* Alterar funcionalidades existentes.
* Adicionar novas funcionalidades.
* Alterar regras de negócio.
* Corrigir problemas.
* Fazer manutenção no código.

Portanto, escrever um código **claro, legível e fácil de modificar** é extremamente importante.

Até a próxima aula! 🚀
