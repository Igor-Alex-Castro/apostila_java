# Aula 06 — Estruturas de Repetição 04

## Exercício — Utilizando `break`

Nesta aula vamos fazer um exercício para praticar o uso do comando `break` dentro de uma estrutura de repetição.

---

# Exercício

Dado o valor de um carro, descubra **em quantas vezes ele pode ser parcelado**, considerando que:

> **O valor mínimo de cada parcela deve ser R$ 1.000,00.**

### Exemplo

Se o carro custa:

```text
R$ 40.000
```

Podemos parcelá-lo em:

```text
40 parcelas de R$ 1.000
```

Portanto, queremos descobrir todas as possibilidades de parcelamento em que o valor de cada parcela seja **maior ou igual a R$ 1.000**.

---

# 1. Definindo o valor do carro

Primeiramente, vamos criar uma variável para armazenar o valor total do carro:

```java
double valorTotal = 30000;
```

Nesse exemplo, estamos trabalhando com um carro de:

```text
R$ 30.000
```

---

# 2. Criando o `for`

Agora precisamos verificar em quantas parcelas podemos dividir esse valor.

Podemos fazer isso utilizando um `for`:

```java
for (int parcela = 1; parcela <= valorTotal; parcela++) {

}
```

Começamos a parcela em `1` porque não existe uma parcela de número `0`.

A cada interação, aumentamos a parcela em `1`:

```java
parcela++;
```

---

# 3. Calculando o valor da parcela

Agora precisamos calcular quanto será o valor de cada parcela.

Para isso:

```java
double valorParcela = valorTotal / parcela;
```

Por exemplo, se:

```text
valorTotal = 30000
parcela = 30
```

Teremos:

```text
30000 / 30 = 1000
```

Então:

```text
30 parcelas de R$ 1.000
```

---

# 4. Verificando o valor mínimo

Agora precisamos verificar se o valor da parcela é maior ou igual a `1000`.

```java
if (valorParcela >= 1000) {
    System.out.println(
        "Parcela: " + parcela +
        " - Valor da parcela: " + valorParcela
    );
}
```

O programa vai encontrar várias possibilidades:

```text
Parcela: 1 - Valor da parcela: 30000
Parcela: 2 - Valor da parcela: 15000
Parcela: 3 - Valor da parcela: 10000
...
Parcela: 30 - Valor da parcela: 1000
```

---

# 5. O problema da primeira solução

Apesar de o código funcionar, temos um problema.

Nosso `for` continua executando até chegar ao valor total:

```java
for (int parcela = 1; parcela <= valorTotal; parcela++) {
```

Se o carro custa `30.000`, o `for` poderá executar aproximadamente **30.000 vezes**.

Porém, nós já sabemos que a partir do momento em que o valor da parcela ficar abaixo de `R$ 1.000`, não encontraremos mais nenhuma possibilidade válida.

Por exemplo:

```text
30 parcelas → R$ 1.000
31 parcelas → aproximadamente R$ 967,74
```

A partir da parcela `31`, o valor continuará diminuindo.

Portanto, não faz sentido continuar executando o laço.

---

# 6. Utilizando `break`

Podemos utilizar o `break` para interromper o `for`.

Uma primeira solução seria:

```java
for (int parcela = 1; parcela <= valorTotal; parcela++) {

    double valorParcela = valorTotal / parcela;

    if (valorParcela >= 1000) {
        System.out.println(
            "Parcela: " + parcela +
            " - Valor da parcela: " + valorParcela
        );
    } else {
        break;
    }
}
```

Agora, quando o valor da parcela for menor que `1000`, o `break` será executado.

Isso faz com que o `for` seja encerrado imediatamente.

---

# 7. Melhorando a lógica

Podemos simplificar ainda mais a lógica.

Em vez de verificar:

```java
if (valorParcela >= 1000) {
    // imprime
} else {
    break;
}
```

Podemos verificar diretamente a condição que indica quando devemos parar:

```java
for (int parcela = 1; parcela <= valorTotal; parcela++) {

    double valorParcela = valorTotal / parcela;

    if (valorParcela < 1000) {
        break;
    }

    System.out.println(
        "Parcela: " + parcela +
        " - Valor da parcela: " + valorParcela
    );
}
```

Essa solução deixa o código mais simples e fácil de entender.

---

# 8. Código completo

```java
public class Aula06EstruturasRepeticao04 {

    public static void main(String[] args) {

        double valorTotal = 30000;

        for (int parcela = 1; parcela <= valorTotal; parcela++) {

            double valorParcela = valorTotal / parcela;

            if (valorParcela < 1000) {
                break;
            }

            System.out.println(
                "Parcela: " + parcela +
                " - Valor da parcela: " + valorParcela
            );
        }
    }
}
```

---

# 9. Como o código funciona

Vamos imaginar que o carro custa:

```text
R$ 30.000
```

O programa começa com:

```text
1 parcela  → R$ 30.000
2 parcelas → R$ 15.000
3 parcelas → R$ 10.000
...
30 parcelas → R$ 1.000
```

Quando chegar em:

```text
31 parcelas → aproximadamente R$ 967,74
```

A condição:

```java
valorParcela < 1000
```

será verdadeira.

Então:

```java
break;
```

será executado.

O `for` será encerrado imediatamente.

---

# 10. Benefício do `break`

Sem o `break`, o programa continuaria executando o `for` mesmo depois de encontrar todas as possibilidades válidas.

Com o `break`, assim que sabemos que não existem mais possibilidades que atendam à regra, podemos interromper o processamento.

No exemplo:

```text
Sem break:
30.000 interações

Com break:
aproximadamente 31 interações
```

Isso evita processamento desnecessário.

---

# Resumo

Neste exercício praticamos novamente o comando:

```java
break;
```

A ideia principal foi:

1. Receber o valor total do carro.
2. Percorrer as possíveis quantidades de parcelas.
3. Calcular o valor de cada parcela.
4. Verificar se a parcela é maior ou igual a `R$ 1.000`.
5. Imprimir as possibilidades válidas.
6. Quando o valor ficar abaixo de `R$ 1.000`, utilizar `break` para sair do laço.

A lógica principal ficou:

```java
if (valorParcela < 1000) {
    break;
}
```

Ou seja:

> **Se a parcela ficar menor que R$ 1.000, não precisamos continuar executando o laço.**

---

## Conceito importante

O `break` deve ser utilizado quando **não existe mais motivo para continuar a execução do laço**.

Nesse exercício, depois que o valor da parcela fica abaixo de `R$ 1.000`, continuar verificando parcelas maiores não traz nenhum resultado válido.

Por isso, podemos interromper o processamento com:

```java
break;
```

Na próxima aula veremos outra situação importante: **quando queremos continuar o laço, mas pular apenas uma determinada interação.**
