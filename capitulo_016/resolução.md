
# Aula 5 — Estruturas Condicionais 05: Resolução do Exercício

## Introdução

Fala, galera! Sejam todos muito bem-vindos novamente ao curso **Maratona Java**.

Muito obrigado a todos vocês que são membros do nosso canal. Vocês são especiais! ❤️

Nesta aula vamos resolver o exercício proposto na aula anterior.

O exercício consiste em descobrir **quanto devemos pagar de imposto com base no salário anual**, utilizando uma tabela de imposto.

---

# Exercício

Na aula anterior, recebemos o seguinte desafio:

> Dado um determinado salário anual, quero saber qual será o valor do imposto que preciso pagar.

Para isso, temos uma tabela com diferentes **faixas salariais** e suas respectivas porcentagens de imposto.

A ideia é verificar em qual faixa o salário anual se encontra e aplicar a porcentagem correspondente.

---

# Criando a classe

Vamos criar uma nova classe para resolver o exercício.

Podemos chamá-la de:

```text
Aula5EstruturasCondicionais05
```

E vamos utilizar o método `main`:

```java
public static void main(String[] args) {

}
```

---

# Começando a implementação

Existem várias maneiras de resolver esse exercício.

A solução apresentada nesta aula **não é a única forma possível**.

O mais importante, principalmente quando estamos aprendendo programação, é primeiro conseguir chegar ao resultado.

Depois podemos analisar o código e verificar como podemos melhorá-lo.

> Primeiro faça funcionar. Depois pense em como melhorar.

---

# Criando a variável do salário

A primeira coisa que precisamos é de uma variável para armazenar o salário anual.

Por exemplo:

```java
double salarioAnual = 60000;
```

Estamos utilizando `double` porque o salário pode possuir valores decimais.

---

# Criando as faixas de imposto

Agora precisamos representar as porcentagens de imposto.

Vamos criar uma variável para cada faixa.

A primeira faixa possui uma taxa de:

```text
9,70%
```

Podemos representar no Java como:

```java
double primeiraFaixa = 9.70 / 100;
```

A segunda faixa possui:

```text
37,35%
```

Então:

```java
double segundaFaixa = 37.35 / 100;
```

E a terceira faixa possui uma porcentagem maior:

```java
double terceiraFaixa = 49.50 / 100;
```

Assim temos:

```java
double primeiraFaixa = 9.70 / 100;
double segundaFaixa = 37.35 / 100;
double terceiraFaixa = 49.50 / 100;
```

Dividimos as porcentagens por `100` para transformá-las em valores que podem ser utilizados diretamente no cálculo.

Por exemplo:

```text
9,70 / 100 = 0,097
```

---

# Criando a variável do imposto

Agora precisamos de uma variável para armazenar o valor do imposto.

Podemos fazer:

```java
double valorImposto = 0;
```

Inicializar a variável com `0` é importante porque vamos atribuir um valor a ela dependendo da faixa salarial.

---

# Primeira condição

Agora precisamos verificar em qual faixa o salário anual está.

A primeira condição verifica se o salário é menor ou igual ao limite da primeira faixa.

```java
if (salarioAnual <= 34613) {
    valorImposto = salarioAnual * primeiraFaixa;
}
```

Nesse caso, se o salário anual for menor ou igual a `34.613`, aplicamos a primeira taxa:

```java
primeiraFaixa
```

---

# Segunda condição

Agora precisamos verificar a segunda faixa.

Para isso, podemos utilizar um `else if`:

```java
else if (salarioAnual >= 34614 && salarioAnual <= 68307) {
    valorImposto = salarioAnual * segundaFaixa;
}
```

Aqui estamos verificando duas condições:

```java
salarioAnual >= 34614
```

e:

```java
salarioAnual <= 68307
```

Como estamos utilizando o operador `&&`, **as duas condições precisam ser verdadeiras**.

Se o salário estiver dentro dessa faixa, aplicamos:

```java
segundaFaixa
```

---

# Terceira faixa

Caso nenhuma das condições anteriores seja verdadeira, podemos considerar que o salário pertence à terceira faixa.

Então utilizamos o `else`:

```java
else {
    valorImposto = salarioAnual * terceiraFaixa;
}
```

Dessa forma, o código fica:

```java
if (salarioAnual <= 34613) {
    valorImposto = salarioAnual * primeiraFaixa;
} else if (salarioAnual >= 34614 && salarioAnual <= 68307) {
    valorImposto = salarioAnual * segundaFaixa;
} else {
    valorImposto = salarioAnual * terceiraFaixa;
}
```

---

# Exibindo o resultado

Depois de calcular o imposto, podemos imprimir o resultado:

```java
System.out.println(valorImposto);
```

O código completo fica:

```java
public class Aula5EstruturasCondicionais05 {
    public static void main(String[] args) {

        double salarioAnual = 60000;

        double primeiraFaixa = 9.70 / 100;
        double segundaFaixa = 37.35 / 100;
        double terceiraFaixa = 49.50 / 100;

        double valorImposto = 0;

        if (salarioAnual <= 34613) {
            valorImposto = salarioAnual * primeiraFaixa;
        } else if (salarioAnual >= 34614 && salarioAnual <= 68307) {
            valorImposto = salarioAnual * segundaFaixa;
        } else {
            valorImposto = salarioAnual * terceiraFaixa;
        }

        System.out.println(valorImposto);
    }
}
```

---

# Testando o programa

Se colocarmos:

```java
double salarioAnual = 60000;
```

O salário estará dentro da segunda faixa.

Portanto, será aplicada:

```java
segundaFaixa
```

O cálculo será:

```text
60000 × 0,3735
```

Resultado:

```text
22410
```

---

# Utilizando o debugger

Uma maneira muito interessante de entender o funcionamento dessas condições é utilizar o **debugger** da IDE.

Podemos colocar um breakpoint na primeira condição:

```java
if (salarioAnual <= 34613) {
```

Depois executamos o programa em modo de debug.

Isso permite acompanhar passo a passo o que o Java está fazendo.

---

# Entendendo o `else if`

Uma parte extremamente importante é entender o comportamento do:

```java
if
else if
else
```

Imagine que temos:

```java
double salarioAnual = 25000;
```

A primeira condição:

```java
if (salarioAnual <= 34613)
```

será verdadeira.

Portanto, o Java entra nesse bloco:

```java
valorImposto = salarioAnual * primeiraFaixa;
```

Depois disso, ele **não continua verificando os próximos `else if`**.

Ele pula toda a cadeia e continua a execução depois do `else`.

---

# Por que isso acontece?

Quando temos:

```java
if (condicao1) {

} else if (condicao2) {

} else {

}
```

O Java verifica as condições de cima para baixo.

Assim que encontra uma condição verdadeira, ele executa aquele bloco e ignora os demais blocos da mesma cadeia.

Por exemplo:

```java
if (condicao1) {
    // executa
} else if (condicao2) {
    // não executa
} else {
    // não executa
}
```

Mesmo que `condicao2` também fosse verdadeira, ela não seria avaliada depois que a primeira condição já tivesse sido satisfeita.

---

# Um exemplo importante

Considere:

```java
double salarioAnual = 25000;
```

Sabemos que:

```java
25000 <= 34613
```

é verdadeiro.

Também é verdade que:

```java
25000 <= 68307
```

Porém, isso não importa.

O primeiro `if` já foi verdadeiro.

Portanto, o Java não precisa avaliar o `else if`.

Esse comportamento é uma das características importantes da cadeia:

```text
if → else if → else
```

---

# Por que ser explícito é importante?

Poderíamos tentar escrever algumas condições de forma mais abreviada.

Por exemplo, poderíamos pensar:

```java
else if (salarioAnual <= 68307)
```

já que sabemos que o primeiro `if` verifica:

```java
salarioAnual <= 34613
```

Porém, prefiro deixar a condição explícita:

```java
else if (salarioAnual >= 34614 && salarioAnual <= 68307)
```

Isso facilita a leitura do código.

Ao olhar rapidamente para a condição, conseguimos entender exatamente qual é a faixa que estamos verificando.

---

# Legibilidade do código

Quando estamos desenvolvendo, principalmente em um código que será mantido por outras pessoas, a legibilidade é muito importante.

Uma condição como:

```java
else if (salarioAnual <= 68307)
```

pode funcionar dependendo da lógica anterior, mas exige que o desenvolvedor analise o `if` anterior para entender completamente o intervalo.

Já:

```java
else if (salarioAnual >= 34614 && salarioAnual <= 68307)
```

deixa explícito:

> O salário precisa estar entre `34.614` e `68.307`.

Isso facilita muito a compreensão.

---

# Cuidado com erros simples

Durante a implementação do exercício, é muito fácil cometer pequenos erros.

Por exemplo, podemos acabar imprimindo:

```java
System.out.println(salarioAnual);
```

quando, na verdade, queremos imprimir:

```java
System.out.println(valorImposto);
```

Nesse caso, o programa pode funcionar perfeitamente, mas apresentar um resultado errado para o objetivo do exercício.

Por isso, é importante sempre verificar:

* Qual variável estou calculando?
* Qual variável estou imprimindo?
* Qual valor está sendo utilizado na multiplicação?
* Qual porcentagem está sendo aplicada?

---

# Outro erro comum

Também precisamos tomar cuidado com a variável que está sendo multiplicada.

O cálculo correto é:

```java
valorImposto = salarioAnual * primeiraFaixa;
```

e não:

```java
valorImposto = valorImposto * primeiraFaixa;
```

Se fizermos:

```java
valorImposto = valorImposto * primeiraFaixa;
```

e `valorImposto` tiver sido inicializado com:

```java
double valorImposto = 0;
```

teremos:

```text
0 × primeiraFaixa = 0
```

Portanto, o resultado será incorreto.

O que queremos calcular é:

```text
salário anual × porcentagem do imposto
```

Ou seja:

```java
valorImposto = salarioAnual * primeiraFaixa;
```

---

# Exemplo do cálculo

Suponha:

```java
double salarioAnual = 30000;
```

E:

```java
double primeiraFaixa = 9.70 / 100;
```

Temos:

```text
30000 × 0,097
```

Resultado:

```text
2910
```

Portanto:

```java
System.out.println(valorImposto);
```

irá imprimir:

```text
2910.0
```

---

# Código final

Uma possível solução para o exercício é:

```java
public class Aula5EstruturasCondicionais05 {
    public static void main(String[] args) {

        double salarioAnual = 60000;

        double primeiraFaixa = 9.70 / 100;
        double segundaFaixa = 37.35 / 100;
        double terceiraFaixa = 49.50 / 100;

        double valorImposto = 0;

        if (salarioAnual <= 34613) {
            valorImposto = salarioAnual * primeiraFaixa;
        } else if (salarioAnual >= 34614 && salarioAnual <= 68307) {
            valorImposto = salarioAnual * segundaFaixa;
        } else {
            valorImposto = salarioAnual * terceiraFaixa;
        }

        System.out.println(valorImposto);
    }
}
```

---

# O que aprendemos?

Nesta aula praticamos diversos conceitos importantes de Java.

### `if`

Utilizamos para verificar a primeira condição:

```java
if (salarioAnual <= 34613) {
```

### `else if`

Utilizamos para verificar uma segunda possibilidade:

```java
else if (salarioAnual >= 34614 && salarioAnual <= 68307) {
```

### `else`

Utilizamos quando nenhuma das condições anteriores foi satisfeita:

```java
else {
```

### Operador `&&`

Utilizamos para exigir que duas condições sejam verdadeiras:

```java
salarioAnual >= 34614 && salarioAnual <= 68307
```

### Variáveis

Utilizamos variáveis para armazenar:

* Salário anual.
* Percentuais de imposto.
* Valor final do imposto.

---

# Conclusão

O mais importante deste exercício não é apenas chegar ao resultado.

Também precisamos entender **como o código está sendo executado**.

Quando temos uma cadeia:

```java
if
else if
else
```

o Java verifica as condições de cima para baixo.

Assim que encontra uma condição verdadeira, executa aquele bloco e ignora os demais.

Também precisamos tomar cuidado com pequenos erros, como:

```java
System.out.println(salarioAnual);
```

quando deveríamos imprimir:

```java
System.out.println(valorImposto);
```

Ou utilizar a variável errada no cálculo.

Esses pequenos detalhes podem fazer com que um programa execute normalmente, mas produza um resultado incorreto.

Por isso:

> **Não basta o código compilar. Precisamos verificar se ele está produzindo o resultado esperado.**

E é isso que tínhamos para falar nesta aula sobre a resolução do exercício.

Até o próximo vídeo! 🚀
