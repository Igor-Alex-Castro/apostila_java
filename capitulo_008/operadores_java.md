# Operadores em Java

## O que são operadores?

Operadores são elementos da linguagem Java que permitem realizar operações com valores e variáveis.

Existem diversos tipos de operadores, mas vamos começar pelos **operadores aritméticos**, responsáveis por realizar cálculos matemáticos.

---

# Operadores Aritméticos

Imagine que temos duas variáveis:

```java
int numero1 = 10;
int numero2 = 20;
```

Os operadores aritméticos básicos são:

| Operador | Função |
|---|---|
| `+` | Soma |
| `-` | Subtração |
| `*` | Multiplicação |
| `/` | Divisão |

---

## Exemplo de Subtração

```java
System.out.println(numero2 - numero1);
```

Resultado:

```text
10
```

---

## Exemplo de Soma

```java
System.out.println(numero1 + numero2);
```

Resultado:

```text
30
```

---

# O Operador `+` e a Sobrecarga

O operador `+` possui dois comportamentos principais:

1. Adição de números.
2. Concatenação de Strings.

---

## 1. Adição de números

```java
System.out.println(numero1 + numero2);
```

Resultado:

```text
30
```

---

## 2. Concatenação de Strings

```java
System.out.println("Valor: " + numero1 + numero2);
```

Resultado:

```text
Valor: 1020
```

Isso acontece porque, após encontrar uma `String`, o Java passa a utilizar o operador `+` como concatenação.

---

# Exemplo da Ordem de Execução

```java
System.out.println(numero1 + numero2 + " Valor");
```

Resultado:

```text
30 Valor
```

Nesse caso:

```text
numero1 + numero2 → 30
```

Depois ocorre a concatenação com a `String` `" Valor"`.

---

# Guardando o Resultado em uma Variável

Também podemos armazenar o resultado da operação em outra variável:

```java
int resultado = numero1 + numero2;

System.out.println(resultado);
```

Resultado:

```text
30
```

---

# Multiplicação

```java
int resultado = numero1 * numero2;

System.out.println(resultado);
```

Resultado:

```text
200
```

---

# Divisão entre Inteiros

```java
int resultado = numero1 / numero2;

System.out.println(resultado);
```

Resultado:

```text
0
```

## Por que o resultado é `0`?

Porque ambos os valores são do tipo `int`.

Quando uma operação é realizada entre dois números inteiros, o resultado também será inteiro.

A parte decimal é descartada.

Matematicamente:

```text
10 ÷ 20 = 0,5
```

Mas em Java:

```text
0
```

---

# Utilizando `double`

Se um dos valores for do tipo `double`:

```java
int numero1 = 10;
double numero2 = 20;

double resultado = numero1 / numero2;

System.out.println(resultado);
```

Resultado:

```text
0.5
```

Agora o Java preserva as casas decimais.

---

# Conversão Explícita (Casting)

Também é possível converter um valor antes da operação:

```java
double resultado = numero1 / (double) numero2;

System.out.println(resultado);
```

Resultado:

```text
0.5
```

O Java primeiro converte `numero2` para `double` e depois realiza a divisão.

---

# Resumo dos Operadores Aritméticos

Operadores aritméticos permitem realizar cálculos matemáticos.

Os operadores básicos são:

- `+` → Soma.
- `-` → Subtração.
- `*` → Multiplicação.
- `/` → Divisão.

O operador `+` pode funcionar como:

- Adição de números.
- Concatenação de `Strings`.

A ordem das operações influencia o resultado.

Operações entre dois `int` resultam em um `int`.

Para obter casas decimais, utilize `double` ou faça casting.

---

# Exemplo Completo

```java
public class Aula04 {

    public static void main(String[] args) {

        int numero1 = 10;
        int numero2 = 20;

        System.out.println(numero1 + numero2); // 30
        System.out.println(numero2 - numero1); // 10
        System.out.println(numero1 * numero2); // 200
        System.out.println(numero1 / numero2); // 0

        System.out.println("Valor: " + numero1 + numero2); // Valor: 1020
        System.out.println(numero1 + numero2 + " Valor"); // 30 Valor

        double resultado = numero1 / (double) numero2;
        System.out.println(resultado); // 0.5
    }

}
```

---

# Operador de Resto e Operadores Relacionais

Nesta aula, continuaremos estudando operadores em Java.

Veremos:

- Operador de resto (`%`).
- Operadores relacionais (comparação).
- Valores booleanos (`true` e `false`).
- Comparação entre diferentes tipos.

---

# Operador de Resto (`%`)

O operador `%` retorna o **resto de uma divisão**.

## Exemplo

```java
int resto = 20 % 2;

System.out.println(resto);
```

Resultado:

```text
0
```

---

# Descobrindo se um Número é Par ou Ímpar

Uma utilização muito comum do operador `%` é verificar se um número é **par ou ímpar**.

---

## Número Par

```java
int numero = 20;

System.out.println(numero % 2);
```

Resultado:

```text
0
```

Se o resto da divisão por `2` for igual a `0`, o número é par.

---

## Número Ímpar

```java
int numero = 7;

System.out.println(numero % 2);
```

Resultado:

```text
1
```

Se o resto da divisão por `2` for diferente de `0`, o número é ímpar.

---

# Operadores Relacionais

Os operadores relacionais são utilizados para **comparar valores**.

Diferentemente dos operadores aritméticos, eles sempre retornam um valor do tipo:

```java
boolean
```

Ou seja:

```java
true  // verdadeiro
false // falso
```

---

# Operadores Relacionais Disponíveis

| Operador | Significado |
|---|---|
| `>` | Maior que |
| `<` | Menor que |
| `>=` | Maior ou igual |
| `<=` | Menor ou igual |
| `==` | Igual |
| `!=` | Diferente |

---

# Maior que (`>`)

```java
boolean resultado = 10 > 20;

System.out.println(resultado);
```

Resultado:

```text
false
```

`10` não é maior que `20`.

---

# Menor que (`<`)

```java
boolean resultado = 10 < 20;

System.out.println(resultado);
```

Resultado:

```text
true
```

`10` é menor que `20`.

---

# Igual (`==`)

## Comparação falsa

```java
boolean resultado = 10 == 20;

System.out.println(resultado);
```

Resultado:

```text
false
```

---

## Comparação verdadeira

```java
boolean resultado = 10 == 10;

System.out.println(resultado);
```

Resultado:

```text
true
```

---

# Diferente (`!=`)

## Comparação falsa

```java
boolean resultado = 10 != 10;

System.out.println(resultado);
```

Resultado:

```text
false
```

---

## Comparação verdadeira

```java
boolean resultado = 10 != 20;

System.out.println(resultado);
```

Resultado:

```text
true
```

---

# Atenção: `=` Não é o Mesmo que `==`

Muitos iniciantes confundem esses dois operadores.

---

## Operador de atribuição

```java
int numero = 10;
```

O sinal `=` atribui um valor à variável.

---

## Operador de comparação

```java
10 == 10
```

Os dois sinais `==` verificam se os valores são iguais.

---

# Comparação entre Tipos Compatíveis

O Java permite comparar tipos numéricos compatíveis.

## Exemplo

```java
boolean resultado = 10 == 10.0;

System.out.println(resultado);
```

Resultado:

```text
true
```

Mesmo sendo um `int` e um `double`, ambos representam o mesmo valor numérico.

---

## Outro Exemplo

```java
boolean resultado = 10 != 10.0;
```

Resultado:

```text
false
```

Os valores são equivalentes.

---

# Comparação entre Tipos Incompatíveis

Não é possível comparar diretamente tipos incompatíveis.

Exemplo:

```java
10 == "10"
```

Isso gera um erro de compilação.

## Por quê?

Porque:

- `10` é um número inteiro (`int`).
- `"10"` é uma `String`.

O Java não permite comparar diretamente esses dois tipos dessa forma.

---

# Observação Sobre Strings

Embora seja possível utilizar `==` em alguns casos com `String`, essa não é a forma correta de comparar textos em Java.

Mais adiante, quando estudarmos `String`, veremos que o método recomendado é:

```java
texto1.equals(texto2);
```

Por enquanto, utilize os exemplos de comparação principalmente com valores numéricos.

---

# Resumo

## Operador de Resto

```text
%
```

Retorna o resto da divisão.

Exemplo:

```java
20 % 2
```

Resultado:

```text
0
```

---

## Operadores Relacionais

```text
>
<
>=
<=
==
!=
```

Sempre retornam:

```text
true
false
```

---

# Exemplos Rápidos

```java
10 > 20   // false
10 < 20   // true
10 == 10  // true
10 != 10  // false
20 % 2    // 0
7 % 2     // 1
```

---

# Código Completo

```java
public class Aula05 {

    public static void main(String[] args) {

        int resto = 20 % 2;
        System.out.println("Resto: " + resto);

        boolean maior = 10 > 20;
        boolean menor = 10 < 20;
        boolean igual = 10 == 10;
        boolean diferente = 10 != 20;

        System.out.println("10 > 20 = " + maior);
        System.out.println("10 < 20 = " + menor);
        System.out.println("10 == 10 = " + igual);
        System.out.println("10 != 20 = " + diferente);
    }

}
```

---

# Conceitos Aprendidos Nesta Aula

- ✅ Operador de resto `%`.
- ✅ Verificar se um número é par ou ímpar.
- ✅ Tipo `boolean`.
- ✅ Operadores relacionais.
- ✅ Diferença entre `=` e `==`.
- ✅ Comparação entre tipos compatíveis e incompatíveis.
