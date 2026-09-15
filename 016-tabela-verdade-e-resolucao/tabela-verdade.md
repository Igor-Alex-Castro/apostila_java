# Aula 5 — Estruturas Condicionais 04: Tabela-Verdade e Exercício

## Introdução

Fala, galera! Sejam todos muito bem-vindos a mais uma aula do curso **Maratona Java**.

Muito obrigado a todos vocês que são membros do nosso canal. Vocês são especiais! ❤️

Na aula de hoje vamos falar sobre a **Tabela-Verdade**.

A Tabela-Verdade é o que vai definir o resultado de uma **expressão booleana** quando temos mais de uma condição.

Na última aula, vimos que podemos utilizar os operadores:

* `&&` — **E**
* `||` — **OU**

Eles permitem verificar se uma ou mais condições são verdadeiras ou falsas.

Agora vamos entender como essas condições se comportam quando são combinadas.

---

# Tabela-Verdade

Quando trabalhamos com mais de uma condição, podemos utilizar principalmente os operadores:

```java
&&
```

e:

```java
||
```

O comportamento de cada um deles é diferente.

---

# Operador `&&` — E

O operador `&&` significa **E**.

Para que o resultado final seja `true`, **todas as condições precisam ser verdadeiras**.

Vamos analisar todas as possibilidades.

| Condição 1 | Condição 2 | Resultado |
| :--------: | :--------: | :-------: |
|   `true`   |   `true`   |   `true`  |
|   `true`   |   `false`  |  `false`  |
|   `false`  |   `true`   |  `false`  |
|   `false`  |   `false`  |  `false`  |

Podemos representar:

```text
true  && true  = true
true  && false = false
false && true  = false
false && false = false
```

## Regra do `&&`

Com o operador **E (`&&`)**, o resultado só será `true` quando **todas as condições forem verdadeiras**.

```text
           &&
          /  \
      true  true
         \  /
        true
```

Se pelo menos uma das condições for `false`, o resultado será `false`.

Por exemplo:

```java
boolean resultado = true && false;
```

O resultado será:

```text
false
```

---

# Operador `||` — OU

Agora vamos analisar o operador:

```java
||
```

Ele significa **OU**.

Diferentemente do `&&`, basta que **uma das condições seja verdadeira** para que o resultado final seja `true`.

Vamos analisar todas as possibilidades:

| Condição 1 | Condição 2 | Resultado |
| :--------: | :--------: | :-------: |
|   `true`   |   `true`   |   `true`  |
|   `true`   |   `false`  |   `true`  |
|   `false`  |   `true`   |   `true`  |
|   `false`  |   `false`  |  `false`  |

Podemos representar:

```text
true  || true  = true
true  || false = true
false || true  = true
false || false = false
```

## Regra do `||`

Com o operador **OU (`||`)**, o resultado só será `false` quando **todas as condições forem falsas**.

Por exemplo:

```java
boolean resultado = false || true;
```

O resultado será:

```text
true
```

---

# Comparando `&&` e `||`

Podemos resumir as regras da seguinte maneira:

### `&&` — E

> Todas as condições precisam ser verdadeiras.

```text
true && true = true
```

Qualquer outra combinação resulta em `false`.

### `||` — OU

> Pelo menos uma condição precisa ser verdadeira.

```text
false || true = true
true  || false = true
true  || true  = true
```

Somente quando todas forem falsas teremos:

```text
false || false = false
```

---

# Resumo da Tabela-Verdade

|    A    |    B    | `A && B` | `A \|\| B` |
| :-----: | :-----: | :------: | :--------: |
|  `true` |  `true` |  `true`  |   `true`   |
|  `true` | `false` |  `false` |   `true`   |
| `false` |  `true` |  `false` |   `true`   |
| `false` | `false` |  `false` |   `false`  |

Uma maneira fácil de lembrar:

```text
&& → todas precisam ser verdadeiras

|| → pelo menos uma precisa ser verdadeira
```

---

# E quando temos várias condições?

A mesma lógica continua valendo quando temos mais de duas condições.

Por exemplo:

```java
boolean resultado = true && true && true && true;
```

Como todas as condições são verdadeiras:

```text
true
```

Agora:

```java
boolean resultado = true && true && false && true;
```

Temos uma condição falsa.

Portanto:

```text
false
```

Já utilizando `||`:

```java
boolean resultado = false || false || false || true;
```

Temos pelo menos uma condição verdadeira.

Portanto:

```text
true
```

E:

```java
boolean resultado = false || false || false || false;
```

Como todas são falsas:

```text
false
```

---

# Regra principal

Podemos guardar duas regras simples:

```text
&& → será verdadeiro se TODAS as condições forem verdadeiras.

|| → será verdadeiro se PELO MENOS UMA condição for verdadeira.
```

Ou ainda:

| Operador | Resultado `true`              |   |                                  |
| :------: | ----------------------------- | - | -------------------------------- |
|   `&&`   | Todas as condições são `true` |   |                                  |
|     `    |                               | ` | Pelo menos uma condição é `true` |

---

# Exercício

Agora vamos fazer um exercício rápido.

Imagine que você está desenvolvendo um programa para calcular o valor de um imposto com base no salário anual.

A ideia é:

> Dado um determinado salário anual, queremos saber qual será o valor do imposto que deverá ser pago.

A entrada do programa será o salário.

Por exemplo:

```java
double salarioAnual = 50000;
```

Com base no salário informado, devemos utilizar uma tabela de faixas para descobrir qual percentual de imposto deve ser aplicado.

---

# Objetivo do exercício

Dado um determinado **salário anual**, queremos calcular o valor que deverá ser pago de imposto.

O programa deverá:

1. Receber o salário anual.
2. Verificar em qual faixa salarial ele se encontra.
3. Identificar a porcentagem correspondente.
4. Calcular o valor do imposto.
5. Exibir o resultado.

---

# Exemplo da lógica

Imagine que tenhamos uma tabela de faixas salariais:

| Faixa salarial                  | Percentual |
| ------------------------------- | ---------- |
| Até determinado valor           | 0%         |
| Entre determinado valor e outro | 10%        |
| Entre determinado valor e outro | 20%        |
| Acima de determinado valor      | 30%        |

O programa deverá verificar em qual faixa o salário informado se encontra.

Por exemplo:

```text
Salário anual → verifica a faixa → aplica a porcentagem → calcula o imposto
```

---

# Entrada

A entrada do programa será o salário anual.

Exemplo:

```java
double salarioAnual = 50000;
```

A partir desse valor, devemos verificar qual faixa corresponde ao salário.

---

# Condições

Para resolver o exercício, podemos utilizar as estruturas condicionais que aprendemos até agora.

Por exemplo:

```java
if (condicao) {
    // primeira faixa
} else if (outraCondicao) {
    // segunda faixa
} else {
    // outra faixa
}
```

O objetivo é utilizar as condições corretamente para identificar a faixa salarial.

---

# Desafio

Agora é com vocês!

Crie um programa Java que:

* Receba um salário anual.
* Verifique a faixa salarial.
* Identifique a porcentagem correspondente.
* Calcule o valor do imposto.
* Exiba o resultado na tela.

Utilize os conhecimentos adquiridos nas aulas anteriores sobre:

* `if`
* `else if`
* `else`
* Operadores relacionais
* Operadores lógicos
* Expressões booleanas
* Tabela-Verdade

---

# Conclusão

Na aula de hoje aprendemos a **Tabela-Verdade** e entendemos como funcionam os operadores lógicos `&&` e `||`.

## Operador `&&`

O resultado será `true` somente quando **todas as condições forem verdadeiras**.

```java
true && true
// true
```

## Operador `||`

O resultado será `true` quando **pelo menos uma condição for verdadeira**.

```java
true || false
// true
```

Portanto:

```text
&& → todas precisam ser verdadeiras

|| → pelo menos uma precisa ser verdadeira
```

Na próxima aula vamos resolver o exercício proposto e colocar em prática tudo o que aprendemos sobre estruturas condicionais.

Até a próxima! 🚀
