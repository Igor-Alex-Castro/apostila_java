# Aula 07 — Estruturas de Repetição 05

## `continue` — O contrário do `break`

Nesta aula vamos falar sobre o comando `continue`, que possui um comportamento diferente do `break`.

---

# 1. Relembrando o `break`

Você já viu que o `break` é utilizado para **sair completamente de um laço de repetição**.

Por exemplo:

```java
for (int i = 0; i <= 50; i++) {

    if (i > 25) {
        break;
    }

    System.out.println(i);
}
```

Quando a condição for verdadeira:

```java
i > 25
```

o `break` será executado e o `for` será encerrado.

Ou seja:

> **`break` interrompe completamente o laço de repetição.**

O `break` também pode ser utilizado dentro de um `switch`.

---

# 2. O que é o `continue`?

O `continue` possui um comportamento diferente.

Enquanto o `break` **sai do laço**, o `continue` apenas **ignora o restante da interação atual** e volta para o início da próxima interação.

Podemos pensar da seguinte maneira:

```text
break
↓
Sai completamente do laço
```

Enquanto:

```text
continue
↓
Ignora o restante da interação
↓
Volta para o início do laço
↓
Continua a próxima interação
```

Portanto:

> **`continue` não encerra o laço. Ele apenas pula a interação atual.**

---

# 3. Exemplo simples

Imagine um `for`:

```java
for (int i = 0; i <= 50; i++) {

    if (i < 30) {
        continue;
    }

    System.out.println(i);
}
```

Enquanto `i` for menor que `30`, o `continue` será executado.

Quando isso acontecer, o Java:

1. Entra no `if`;
2. Executa o `continue`;
3. Ignora tudo que estiver abaixo dele;
4. Volta para o início do `for`;
5. Continua com a próxima interação.

Por isso, o `System.out.println()` não será executado para os valores menores que `30`.

Quando `i` chegar a `30`, a condição:

```java
i < 30
```

será falsa.

Então o `continue` não será executado e o código abaixo dele poderá continuar normalmente.

---

# 4. Exercício com `continue`

Vamos utilizar novamente o exemplo do parcelamento do carro.

Suponha que temos:

```java
double valorTotal = 30000;
```

Queremos verificar as possibilidades de parcelamento.

Porém, dessa vez vamos começar com a quantidade máxima de parcelas e diminuir até chegar a `1`.

```java
for (int parcela = (int) valorTotal; parcela >= 1; parcela--) {

}
```

Como estamos trabalhando com um `double`, precisamos fazer a conversão para `int` para utilizar o valor como contador:

```java
(int) valorTotal
```

Assim, para um carro de `R$ 30.000`, o `for` começará em:

```text
30000
```

e irá diminuindo:

```text
30000
29999
29998
29997
...
3
2
1
```

---

# 5. Calculando o valor da parcela

Dentro do `for`, calculamos o valor da parcela:

```java
double valorParcela = valorTotal / parcela;
```

Agora podemos verificar quando o valor da parcela ainda é menor que `R$ 1.000`.

```java
if (valorParcela < 1000) {
    continue;
}
```

Isso significa:

> Enquanto o valor da parcela for menor que R$ 1.000, ignore o restante dessa interação e continue o `for`.

---

# 6. Código completo

```java
double valorTotal = 30000;

for (int parcela = (int) valorTotal; parcela >= 1; parcela--) {

    double valorParcela = valorTotal / parcela;

    if (valorParcela < 1000) {
        continue;
    }

    System.out.println(
        "Parcela: " + parcela +
        " - Valor da parcela: " + valorParcela
    );
}
```

---

# 7. O que acontece nesse código?

O `for` começa com:

```text
parcela = 30000
```

Nesse caso:

```text
30000 / 30000 = 1
```

Como `1` é menor que `1000`, o código executa:

```java
continue;
```

Então o `System.out.println()` é ignorado.

O `for` continua para a próxima interação:

```text
parcela = 29999
```

E assim por diante.

Todos os valores de parcela que resultarem em menos de `R$ 1.000` serão simplesmente ignorados.

Quando chegarmos a:

```text
parcela = 30
```

teremos:

```text
30000 / 30 = 1000
```

Agora:

```java
valorParcela < 1000
```

será `false`.

Portanto, o `continue` não será executado e o código abaixo será executado:

```java
System.out.println(
    "Parcela: " + parcela +
    " - Valor da parcela: " + valorParcela
);
```

Resultado:

```text
Parcela: 30 - Valor da parcela: 1000
```

---

# 8. Diferença entre `break` e `continue`

Essa é uma diferença muito importante.

## `break`

O `break` **encerra completamente o laço**.

```java
if (condicao) {
    break;
}
```

Fluxo:

```text
Laço
 ↓
Condição
 ↓
break
 ↓
SAI DO LAÇO
```

---

## `continue`

O `continue` **não encerra o laço**.

Ele apenas ignora o restante da interação atual.

```java
if (condicao) {
    continue;
}
```

Fluxo:

```text
Laço
 ↓
Condição
 ↓
continue
 ↓
Ignora o restante da interação
 ↓
Próxima interação
```

---

# 9. Por que utilizar `continue`?

Imagine que dentro de um `for` você tenha várias operações:

```java
for (...) {

    // operação 1

    // operação 2

    // operação 3

    // operação 4

    // operação 5
}
```

Porém, em determinada situação, você não precisa executar as operações seguintes.

Nesse caso, pode utilizar:

```java
continue;
```

Assim, você evita executar o restante daquela interação e passa diretamente para a próxima.

Isso pode ser especialmente importante em situações reais em que existem operações mais pesadas, como:

* Consultas ao banco de dados;
* Conexões com serviços externos;
* Chamadas de APIs;
* Processamentos mais complexos;
* Operações que consomem mais recursos.

---

# 10. Um exemplo conceitual

Imagine:

```java
for (...) {

    if (condicao) {
        continue;
    }

    // código pesado
    // consulta no banco
    // chamada de serviço
    // processamento
}
```

Se a condição for verdadeira, o Java executará:

```java
continue;
```

e não executará o código pesado daquela interação.

Em seguida, ele continuará o `for` normalmente.

---

# Resumo

| Comando    | Comportamento                            |
| ---------- | ---------------------------------------- |
| `break`    | Sai completamente do laço                |
| `continue` | Pula a interação atual e continua o laço |

### `break`

```java
if (condicao) {
    break;
}
```

➡️ **Encerra o laço.**

### `continue`

```java
if (condicao) {
    continue;
}
```

➡️ **Ignora o restante da interação e vai para a próxima.**

---

## Conceito principal

O `continue` é mais uma ferramenta disponível para controlar a execução dos nossos laços de repetição.

Ele é útil quando queremos dizer:

> **"Nesta interação não preciso executar o restante do código. Pode continuar para a próxima."**

Já o `break` significa:

> **"Não preciso mais continuar esse laço. Pode sair completamente."**

Na próxima aula, veremos outras possibilidades de controle dos laços de repetição.
