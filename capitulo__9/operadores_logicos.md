# Operadores Lógicos em Java

Nesta aula, vamos continuar estudando operadores em Java, focando nos **operadores lógicos**.

Antes disso, vamos relembrar os operadores relacionais.

---

# Revisão dos Operadores Relacionais

| Operador | Significado |
|---|---|
| `>=` | Maior ou igual |
| `<=` | Menor ou igual |

## Exemplos

### Maior ou igual

```java
10 >= 20
```

Resultado:

```text
false
```

---

### Menor ou igual

```java
10 <= 20
```

Resultado:

```text
true
```

Esses operadores funcionam da mesma forma que os operadores relacionais vistos anteriormente.

---

# Operadores Lógicos

Os operadores lógicos são utilizados para **combinar condições**.

Eles trabalham com expressões que retornam valores booleanos:

```java
true
false
```

Existem três operadores lógicos principais em Java:

| Operador | Significado |

 `&&` AND (E) 
 
 `||` OR (OU) 
 
`!` NOT (NÃO) 


Nesta aula, veremos principalmente os operadores `&&`, `||` e `!`.

---

# Operador AND (`&&`)

O operador `&&` significa **"E"**.

Exemplos do dia a dia:

- Minha casa é grande **e** espaçosa.
- Vou comprar banana **e** morango.

Em programação:

```java
condicao1 && condicao2
```

O resultado só será verdadeiro quando **ambas as condições forem verdadeiras**.

---

# Operador OR (`||`)

O operador `||` significa **"OU"**.

Exemplos:

- Vou sair se tiver dinheiro **ou** alguém me levar.
- Vou à festa se tiver dinheiro para o táxi **ou** conseguir uma carona.

Em Java:

```java
condicao1 || condicao2
```

Basta **uma das condições ser verdadeira** para o resultado ser verdadeiro.

---

# Operador NOT (`!`)

O operador `!` representa **negação**.

Ele inverte o valor booleano.

## Exemplo

```java
!true
```

Resultado:

```text
false
```

---

Outro exemplo:

```java
!false
```

Resultado:

```text
true
```

---

# Exemplo Prático

Imagine uma regra salarial para trabalhadores na Holanda.

Para estar dentro da legislação:

### Pessoas com 30 anos ou mais

Devem receber pelo menos:

```text
4612 euros
```

### Pessoas com menos de 30 anos

Devem receber pelo menos:

```text
3381 euros
```

Vamos criar um sistema que verifica se a pessoa está dentro dessas regras.

---

# Variáveis

```java
int idade = 35;
double salario = 3500;
```

---

# Verificando Quem Tem 30 Anos ou Mais

```java
boolean estaDentroDaLeiMaiorQue30 =
        idade >= 30 && salario >= 4612;
```

Observe que utilizamos:

```java
&&
```

Porque **ambas as condições precisam ser verdadeiras**.

---

# Avaliação

## Primeira condição

```java
idade >= 30
```

Resultado:

```text
true
```

---

## Segunda condição

```java
salario >= 4612
```

Resultado:

```text
false
```

Como uma das condições é falsa:

```text
true && false
```

Resultado final:

```text
false
```

A pessoa **não está dentro da regra**.

---

# Verificando Quem Tem Menos de 30 Anos

```java
boolean estaDentroDaLeiMenorQue30 =
        idade < 30 && salario >= 3381;
```

---

# Exemplo

```java
int idade = 29;
double salario = 3500;
```

## Primeira condição

```java
idade < 30
```

Resultado:

```text
true
```

---

## Segunda condição

```java
salario >= 3381
```

Resultado:

```text
true
```

---

## Resultado Final

```text
true && true
```

Resultado:

```text
true
```

A pessoa **está dentro da regra**.

---

# Entendendo o AND (`&&`)

O operador AND exige que **todas as condições sejam verdadeiras**.

| Condição 1 | Condição 2 | Resultado |
|---|---|---|
| `true` | `true` | `true` |
| `true` | `false` | `false` |
| `false` | `true` | `false` |
| `false` | `false` | `false` |

Se apenas **uma condição for falsa**, o resultado já será `false`.

---

# Código Completo

```java
public class Aula06 {

    public static void main(String[] args) {

        int idade = 29;
        double salario = 3500;

        boolean estaDentroDaLeiMaiorQue30 =
                idade >= 30 && salario >= 4612;

        boolean estaDentroDaLeiMenorQue30 =
                idade < 30 && salario >= 3381;

        System.out.println(
                "Está dentro da lei para maiores de 30? "
                        + estaDentroDaLeiMaiorQue30);

        System.out.println(
                "Está dentro da lei para menores de 30? "
                        + estaDentroDaLeiMenorQue30);
    }

}
```

---

# Resumo da Aula

- ✅ Revisão dos operadores `>=` e `<=`.

- ✅ Operadores lógicos:

  - `&&` → E (AND).
  - `||` → OU (OR).
  - `!` → NÃO (NOT).

- ✅ O operador `&&` exige que todas as condições sejam verdadeiras.

- ✅ O operador `||` retorna `true` quando pelo menos uma das condições é verdadeira.

- ✅ O operador `!` inverte um valor booleano.

- ✅ Uso de operadores lógicos para validar regras de negócio.

- ✅ Introdução às estruturas condicionais que serão aprofundadas nas próximas aulas.
