# Operadores de Atribuição e Incremento em Java

## Introdução

Nesta aula, vamos continuar estudando os operadores em Java.

Agora veremos os **operadores de atribuição** e os **operadores de incremento e decremento**.

---

# Operadores de Atribuição

Os operadores de atribuição são utilizados para **atribuir valores às variáveis**.

Você já conhece um dos principais:

```java
=
```

O operador `=` é utilizado para atribuir um valor a uma variável.

Exemplo:

```java
int numero = 10;
```

Nesse caso, o valor `10` é atribuído à variável `numero`.

---

# Operadores de Atribuição Composta

Além do operador `=`, Java possui operadores de atribuição compostos.

Eles foram criados para simplificar o código e evitar repetições desnecessárias.

Os principais são:

| Operador | Exemplo | Equivalente |
|---|---|---|
| `+=` | `numero += 10` | `numero = numero + 10` |
| `-=` | `numero -= 10` | `numero = numero - 10` |
| `*=` | `numero *= 10` | `numero = numero * 10` |
| `/=` | `numero /= 10` | `numero = numero / 10` |
| `%=` | `numero %= 10` | `numero = numero % 10` |

---

# Operador `+=`

Imagine que temos um bônus de **R$ 1.800,00**:

```java
double bonus = 1800;
```

Agora queremos adicionar mais **R$ 1.000,00** ao bônus.

Uma forma de fazer isso seria:

```java
bonus = bonus + 1000;
```

Nesse caso, o Java pega o valor atual de `bonus`, adiciona `1000` e atribui o novo resultado à própria variável.

Depois dessa operação:

```text
bonus = 2800
```

Podemos simplificar utilizando o operador `+=`:

```java
bonus += 1000;
```

Essa instrução é equivalente a:

```java
bonus = bonus + 1000;
```

O resultado será o mesmo:

```text
2800
```

---

# Por que utilizar `+=`?

O operador de atribuição composta deixa o código mais curto e fácil de escrever.

Em vez de:

```java
bonus = bonus + 1000;
```

Podemos escrever:

```java
bonus += 1000;
```

Essa forma é bastante utilizada no desenvolvimento Java.

---

# Operador `-=`

O operador `-=` é utilizado para subtrair um valor da própria variável.

Exemplo:

```java
double bonus = 2800;

bonus -= 1000;
```

É equivalente a:

```java
bonus = bonus - 1000;
```

Resultado:

```text
1800
```

---

# Operador `*=`

O operador `*=` é utilizado para multiplicar o valor da variável.

Exemplo:

```java
double bonus = 1800;

bonus *= 2;
```

É equivalente a:

```java
bonus = bonus * 2;
```

Resultado:

```text
3600
```

---

# Operador `/=`

O operador `/=` é utilizado para dividir o valor da variável.

Exemplo:

```java
double bonus = 1800;

bonus /= 2;
```

É equivalente a:

```java
bonus = bonus / 2;
```

Resultado:

```text
900
```

---

# Operador `%=`

O operador `%=` é utilizado para obter o resto da divisão e armazená-lo na própria variável.

Exemplo:

```java
int numero = 10;

numero %= 3;
```

É equivalente a:

```java
numero = numero % 3;
```

Como:

```text
10 % 3 = 1
```

O resultado será:

```text
numero = 1
```

---

# Operadores de Incremento e Decremento

Além dos operadores de atribuição, existem operadores utilizados para realizar incrementos e decrementos.

Os principais são:

```java
++
--
```

O operador `++` incrementa o valor de uma variável em `1`.

O operador `--` decrementa o valor de uma variável em `1`.

---

# Incrementando uma Variável

Imagine que temos uma variável chamada `contador`:

```java
int contador = 0;
```

Podemos adicionar `1` utilizando o operador `+=`:

```java
contador += 1;
```

Isso é equivalente a:

```java
contador = contador + 1;
```

Após a execução:

```text
contador = 1
```

---

# Utilizando o Operador `++`

Existe uma forma ainda mais abreviada de incrementar uma variável em `1`:

```java
contador++;
```

Isso é equivalente a:

```java
contador += 1;
```

E também:

```java
contador = contador + 1;
```

O operador `++` é muito utilizado em estruturas de repetição, como veremos posteriormente.

---

# Operador `--`

Da mesma forma que temos o operador `++`, temos o operador `--`.

Ele decrementa o valor da variável em `1`.

Exemplo:

```java
int contador = 2;

contador--;
```

É equivalente a:

```java
contador -= 1;
```

E também:

```java
contador = contador - 1;
```

Após a execução:

```text
contador = 1
```

---

# Pré-Incremento e Pós-Incremento

É importante entender que existe uma diferença entre colocar o operador `++` **antes** ou **depois** da variável.

Temos:

### Pós-incremento

```java
contador++;
```

### Pré-incremento

```java
++contador;
```

A diferença está no momento em que o incremento acontece em relação à utilização do valor da variável na expressão.

---

# Pós-Incremento (`contador++`)

Quando utilizamos:

```java
contador++;
```

O valor atual da variável é utilizado primeiro e, depois, a variável é incrementada.

Exemplo:

```java
int contador = 0;

System.out.println(contador++);
System.out.println(contador);
```

Saída:

```text
0
1
```

Na primeira instrução:

```java
System.out.println(contador++);
```

O valor atual de `contador` é `0`.

Esse valor é utilizado pelo `println` e, depois, o contador é incrementado.

O fluxo é:

```text
1. Utiliza o valor atual
2. Incrementa a variável
```

---

# Pré-Incremento (`++contador`)

Quando utilizamos:

```java
++contador;
```

A variável é incrementada primeiro e, depois, o novo valor é utilizado na expressão.

Exemplo:

```java
int contador = 0;

System.out.println(++contador);
System.out.println(contador);
```

Saída:

```text
1
1
```

Nesse caso, o fluxo é:

```text
1. Incrementa a variável
2. Utiliza o novo valor
```

---

# Comparando Pré-Incremento e Pós-Incremento

| Operador | Ordem de execução |
|---|---|
| `contador++` | Utiliza o valor e depois incrementa |
| `++contador` | Incrementa e depois utiliza o valor |

Exemplo:

```java
int contador = 0;

System.out.println(contador++);
```

Resultado:

```text
0
```

Depois da execução:

```text
contador = 1
```

Agora utilizando:

```java
int contador = 0;

System.out.println(++contador);
```

Resultado:

```text
1
```

Depois da execução:

```text
contador = 1
```

A variável termina com o mesmo valor nos dois casos. A diferença está no **momento em que o valor é utilizado na expressão**.

---

# Decremento Pré e Pós

A mesma lógica se aplica ao operador `--`.

## Pós-decremento

```java
contador--;
```

Primeiro utiliza o valor atual e depois decrementa.

---

## Pré-decremento

```java
--contador;
```

Primeiro decrementa e depois utiliza o novo valor.

---

# Exemplo Completo

```java
public class Aula08 {

    public static void main(String[] args) {

        double bonus = 1800;

        // Atribuição composta
        bonus += 1000;

        System.out.println("Bônus após adicionar R$ 1.000,00: " + bonus);

        // Subtração
        bonus -= 500;

        System.out.println("Bônus após retirar R$ 500,00: " + bonus);

        // Multiplicação
        bonus *= 2;

        System.out.println("Bônus após multiplicar por 2: " + bonus);

        // Divisão
        bonus /= 2;

        System.out.println("Bônus após dividir por 2: " + bonus);

        // Incremento
        int contador = 0;

        contador++;

        System.out.println("Contador: " + contador);

        // Decremento
        contador--;

        System.out.println("Contador: " + contador);
    }

}
```

---

# Resumo

## Operadores de Atribuição

O operador básico de atribuição é:

```java
=
```

Ele atribui um valor a uma variável.

---

## Operadores de Atribuição Composta

| Operador | Exemplo | Equivalente |
|---|---|---|
| `+=` | `numero += 1` | `numero = numero + 1` |
| `-=` | `numero -= 1` | `numero = numero - 1` |
| `*=` | `numero *= 2` | `numero = numero * 2` |
| `/=` | `numero /= 2` | `numero = numero / 2` |
| `%=` | `numero %= 2` | `numero = numero % 2` |

---

## Operadores de Incremento e Decremento

```java
++
--
```

O operador `++` incrementa uma variável em `1`.

O operador `--` decrementa uma variável em `1`.

---

## Pré e Pós-Incremento

### Pós-incremento

```java
contador++;
```

Utiliza o valor atual e depois incrementa.

### Pré-incremento

```java
++contador;
```

Incrementa primeiro e depois utiliza o novo valor.

A mesma lógica se aplica ao decremento:

```java
contador--;
--contador;
```

---

# Conceitos Aprendidos Nesta Aula

- ✅ Operador de atribuição `=`.
- ✅ Operadores de atribuição composta.
- ✅ Operador `+=`.
- ✅ Operador `-=`.
- ✅ Operador `*=`.
- ✅ Operador `/=`.
- ✅ Operador `%=`.
- ✅ Operador de incremento `++`.
- ✅ Operador de decremento `--`.
- ✅ Pré-incremento.
- ✅ Pós-incremento.
- ✅ Pré-decremento.
- ✅ Pós-decremento.
- ✅ Diferença entre `contador++` e `++contador`.
