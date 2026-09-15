# Operador OR (`||`) em Java

Nesta aula, vamos continuar estudando os **operadores lógicos**, focando no operador **OU (OR)**.

Você já viu o operador **AND (`&&`)**, onde todas as condições precisam ser verdadeiras.

Agora veremos o operador que funciona de forma diferente: o **OU (`||`)**.

---

# Operador OR (`||`)

O operador OR significa **"OU"**.

Ele é utilizado quando **apenas uma das condições precisa ser verdadeira** para o resultado final ser verdadeiro.

---

# Exemplo do Dia a Dia

Imagine a seguinte situação:

> Vou comprar um PlayStation 5 se tiver dinheiro na conta corrente **OU** na poupança.

Se uma das contas tiver saldo suficiente, já é suficiente para realizar a compra.

Em programação:

```java
condicao1 || condicao2
```

Basta uma das condições ser verdadeira para o resultado ser `true`.

---

# Cenário Prático

Vamos simular duas contas bancárias:

```java
double contaCorrente = 200;
double contaPoupanca = 3000;
```

E o valor de um PlayStation 5:

```java
double valorPlaystation = 5000;
```

---

# Objetivo

Descobrir se é possível comprar o PlayStation usando:

- Conta corrente **OU**
- Conta poupança.

---

# Variável de Resultado

Podemos criar uma variável booleana para armazenar o resultado:

```java
boolean playstationCompravel;
```

---

# Usando o Operador OR (`||`)

```java
playstationCompravel =
        contaCorrente >= valorPlaystation ||
        contaPoupanca >= valorPlaystation;
```

Nesse caso, estamos verificando duas condições:

```java
contaCorrente >= valorPlaystation
```

**OU**

```java
contaPoupanca >= valorPlaystation
```

---

# Como a Lógica Funciona

## Primeira Condição

```java
contaCorrente >= valorPlaystation
```

Substituindo os valores:

```text
200 >= 5000
```

Resultado:

```text
false
```

A conta corrente não possui saldo suficiente.

---

## Segunda Condição

```java
contaPoupanca >= valorPlaystation
```

Substituindo os valores:

```text
3000 >= 5000
```

Resultado:

```text
false
```

A conta poupança também não possui saldo suficiente.

---

# Resultado Final

No nosso caso:

```text
false || false
```

Resultado:

```text
false
```

Portanto, não é possível comprar o PlayStation com nenhuma das duas contas.

---

# Regra do Operador OR (`||`)

O operador OR retorna `true` quando **pelo menos uma das condições é verdadeira**.

| Condição 1 | Condição 2 | Resultado |
|---|---|---|
| `true` | `true` | `true` |
| `true` | `false` | `true` |
| `false` | `true` | `true` |
| `false` | `false` | `false` |

A única situação em que o resultado será `false` é quando **todas as condições forem falsas**.

---

# Exemplo Completo do Programa

```java
public class Aula07 {

    public static void main(String[] args) {

        double contaCorrente = 200;
        double contaPoupanca = 3000;

        double valorPlaystation = 5000;

        boolean playstationCompravel =
                contaCorrente >= valorPlaystation ||
                contaPoupanca >= valorPlaystation;

        System.out.println(
                "É possível comprar o PlayStation? "
                        + playstationCompravel
        );
    }

}
```

Saída:

```text
É possível comprar o PlayStation? false
```

---

# Exemplo com Uma Condição Verdadeira

Agora imagine que a conta poupança tenha saldo suficiente:

```java
double contaCorrente = 200;
double contaPoupanca = 6000;

double valorPlaystation = 5000;
```

A avaliação será:

```text
contaCorrente >= valorPlaystation
```

Resultado:

```text
false
```

E:

```text
contaPoupanca >= valorPlaystation
```

Resultado:

```text
true
```

Aplicando o operador OR:

```text
false || true
```

Resultado:

```text
true
```

Nesse caso, é possível comprar o PlayStation porque **uma das contas possui saldo suficiente**.

---

# Explicação Importante: Short-Circuit

No operador `||`, basta uma condição ser verdadeira para o resultado final ser `true`.

Se a primeira condição já for verdadeira, o Java pode não precisar verificar a segunda condição.

Esse comportamento é chamado de **short-circuit** (curto-circuito).

Exemplo:

```java
true || algumaCondicao
```

Como a primeira condição já é `true`, o resultado será:

```text
true
```

A segunda condição não precisa ser avaliada.

Isso pode ajudar na otimização da execução do programa e também é importante quando a segunda expressão possui algum efeito colateral.

---

# Diferença entre AND e OR

| Operador | Nome | Regra |


 `&&`  AND (E)  Todas as condições precisam ser verdadeiras 
 
 `||`  OR (OU)  Pelo menos uma condição precisa ser verdadeira 

---

# Exemplo Comparativo

## AND (`&&`)

```java
idade > 18 && salario > 3000
```

Nesse caso, as duas condições precisam ser verdadeiras.

Exemplo:

```text
idade > 18 → true
salario > 3000 → true
```

Resultado:

```text
true && true = true
```

Se uma das condições for falsa:

```text
true && false = false
```

---

## OR (`||`)

```java
idade > 18 || salario > 3000
```

Nesse caso, apenas uma das condições precisa ser verdadeira.

Exemplo:

```text
idade > 18 → true
salario > 3000 → false
```

Resultado:

```text
true || false = true
```

---

# Resumo da Aula

- ✅ Operador OR (`||`).
- ✅ Basta **UMA condição** ser verdadeira para o resultado ser `true`.
- ✅ Se todas as condições forem falsas, o resultado será `false`.
- ✅ O operador `||` é utilizado para validar múltiplas possibilidades.
- ✅ O operador `&&` exige que todas as condições sejam verdadeiras.
- ✅ O operador `||` exige que pelo menos uma condição seja verdadeira.
- ✅ O Java utiliza o conceito de **short-circuit** na avaliação do operador `||`.
````
