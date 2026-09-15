# Aula 06 — Estruturas de Repetição 03

## `break` — Interrompendo um laço de repetição

Nesta aula vamos aprender como **parar uma iteração** e sair de um laço de repetição utilizando o comando `break`.

O `break` também pode ser utilizado em um `switch`, como vimos anteriormente.

---

# Exercício

Vamos começar com um problema simples:

> Dado um número de `0` a `50`, quero imprimir os primeiros `25` números e, depois disso, parar a execução do laço de repetição.

Por exemplo, se temos:

```java
int max = 50;
```

Queremos percorrer os números de `0` até `50`, mas imprimir somente os primeiros `25`.

---

# Primeira solução

Podemos começar utilizando um `for`:

```java
int max = 50;

for (int i = 0; i <= max; i++) {
    if (i <= 25) {
        System.out.println(i);
    }
}
```

Nesse caso, o programa vai imprimir:

```text
0
1
2
3
...
24
25
```

Porém, existe um problema.

Mesmo depois de chegar ao número `25`, o `for` continua executando até chegar ao `50`.

Ou seja, estamos fazendo o laço continuar mesmo quando já não precisamos mais dele.

---

# O problema do processamento desnecessário

Imagine que depois do `if` existam outras operações mais complexas.

O programa continuaria executando o laço até `50`, mesmo que já tivéssemos encontrado o resultado desejado.

Nesse caso, podemos simplesmente dizer:

> "Quando chegar a determinada condição, saia do laço."

É exatamente isso que o `break` faz.

---

# Utilizando o `break`

Podemos alterar o código para:

```java
int max = 50;

for (int i = 0; i <= max; i++) {

    if (i > 25) {
        break;
    }

    System.out.println(i);
}
```

Agora o comportamento é diferente.

O programa começa imprimindo:

```text
0
1
2
3
...
24
25
```

Quando `i` chegar a `26`, teremos:

```java
i > 25
```

Ou seja:

```text
26 > 25 → true
```

Nesse momento, o `break` será executado.

---

# O que o `break` faz?

O comando:

```java
break;
```

**interrompe imediatamente o laço de repetição em que ele está.**

No nosso exemplo:

```java
if (i > 25) {
    break;
}
```

Quando a condição for verdadeira, o `for` será encerrado.

Portanto, o programa não continuará:

```text
27
28
29
30
...
50
```

Ele simplesmente sairá do `for`.

---

# Fluxo da execução

Podemos visualizar dessa maneira:

```text
i = 0
  ↓
i > 25?
  ↓
false
  ↓
imprime 0
  ↓
i++
  ↓
...
  ↓
i = 25
  ↓
25 > 25?
  ↓
false
  ↓
imprime 25
  ↓
i++
  ↓
i = 26
  ↓
26 > 25?
  ↓
true
  ↓
break
  ↓
sai do for
```

---

# `break` não é `continue`

É importante não confundir `break` com outros comandos de controle de fluxo.

O `break`:

> **Encerra o laço completamente.**

Por exemplo:

```java
for (int i = 0; i <= 50; i++) {

    if (i > 25) {
        break;
    }

    System.out.println(i);
}
```

Quando chegar em `26`, o `for` termina.

---

# `break` também pode ser utilizado em `switch`

O `break` não é exclusivo dos laços de repetição.

Como vimos anteriormente, ele também pode ser utilizado em um `switch`:

```java
switch (dia) {

    case 1:
        System.out.println("Domingo");
        break;

    case 2:
        System.out.println("Segunda-feira");
        break;
}
```

Nesse caso, o `break` faz o programa sair do `switch`.

Portanto, podemos utilizar `break` para interromper:

* Um laço de repetição.
* Um `switch`.

---

# `break` dentro de um `if`

O `break` pode aparecer dentro de um `if`, desde que esse `if` esteja dentro de uma estrutura que permita o `break`.

Por exemplo:

```java
for (int i = 0; i <= 50; i++) {

    if (i > 25) {
        break;
    }

    System.out.println(i);
}
```

Aqui o `break` está dentro do `if`, mas ele está associado ao `for` que o envolve.

O `if` apenas determina **quando** o `break` será executado.

---

# Exemplo completo

```java
public class Aula06EstruturasRepeticao03 {

    public static void main(String[] args) {

        int max = 50;

        for (int i = 0; i <= max; i++) {

            if (i > 25) {
                break;
            }

            System.out.println(i);
        }
    }
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
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
```

---

# Outra forma de pensar

O `break` pode ser entendido como:

> **"Pare a execução do laço agora e saia dele."**

Por exemplo:

```java
if (i > 25) {
    break;
}
```

Pode ser interpretado como:

> "Se `i` for maior que `25`, não preciso continuar executando esse laço. Saia dele."

---

# Por que utilizar `break`?

O `break` é útil quando sabemos que **não precisamos continuar executando o laço** depois que determinada condição acontece.

Isso pode evitar processamento desnecessário.

No nosso exercício, depois de chegar ao número `26`, já sabemos que não queremos mais imprimir nada.

Então não existe motivo para continuar executando o `for` até `50`.

Em vez disso:

```java
if (i > 25) {
    break;
}
```

encerra o laço imediatamente.

---

# Resumo

Nesta aula aprendemos o comando:

```java
break;
```

Ele serve para **interromper a execução de um laço de repetição** ou de um `switch`.

### Exemplo em um `for`

```java
for (int i = 0; i <= 50; i++) {

    if (i > 25) {
        break;
    }

    System.out.println(i);
}
```

Quando `i` chegar a `26`:

```text
26 > 25 → true
```

O `break` será executado e o `for` será encerrado.

---

# Pontos importantes

* `break` interrompe imediatamente o laço.
* Ele faz o programa sair do `for`, `while` ou `do-while` em que está.
* Também pode ser utilizado em `switch`.
* O `if` pode ser usado para determinar quando o `break` deve acontecer.
* Utilizar `break` pode evitar processamento desnecessário quando não precisamos continuar o laço.

---

## Conclusão

O `break` é um comando de **controle de fluxo** que permite interromper uma execução antes que a condição normal do laço seja finalizada.

No próximo exercício vamos praticar melhor o funcionamento do `break`.

Até a próxima aula! 🚀
