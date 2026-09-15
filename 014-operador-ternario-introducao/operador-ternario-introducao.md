# Aula 5 — Estruturas Condicionais 03: Operador Ternário

## Introdução

Fala, galera! Sejam todos muito bem-vindos a mais uma aula do curso **Maratona Java**.

Muito obrigado a todos vocês que acompanham o nosso canal. Vocês são especiais e moram no meu coração! ❤️

Hoje vamos falar sobre o **operador ternário**, que foi criado no Java para simplificar determinadas condições `if/else`, principalmente quando precisamos **associar diretamente um valor a uma variável** ou utilizar o resultado de uma condição como retorno de um método.

---

# O problema

Vamos começar com um problema simples.

Imagine que eu queira decidir se vou fazer uma doação de **R$ 500,00 para o DevDojo**.

Porém, só posso fazer essa doação se o meu salário for **maior que R$ 5.000,00**.

Primeiro, vamos criar uma variável para representar o salário:

```java
int salario = 6000;
```

Agora queremos criar uma mensagem informando se podemos ou não fazer a doação.

```java
String mensagemDoar = "Eu vou doar R$ 500,00 para o DevDojo";
String mensagemNaoDoar = "Eu ainda não tenho condições de doar para o DevDojo";
```

Temos duas possíveis mensagens:

* Se o salário for maior que `5000`, vamos utilizar a mensagem de doação.
* Caso contrário, vamos utilizar a mensagem informando que ainda não temos condições.

---

# Fazendo com `if/else`

A forma tradicional seria utilizar uma estrutura `if/else`:

```java
String resultado;

if (salario > 5000) {
    resultado = mensagemDoar;
} else {
    resultado = mensagemNaoDoar;
}

System.out.println(resultado);
```

Se o salário for:

```java
int salario = 6000;
```

O resultado será:

```text
Eu vou doar R$ 500,00 para o DevDojo
```

Agora, se alterarmos para:

```java
int salario = 3000;
```

Teremos:

```text
Eu ainda não tenho condições de doar para o DevDojo
```

Como podemos perceber, estamos simplesmente escolhendo qual valor será atribuído à variável `resultado`.

É justamente nesse tipo de situação que podemos utilizar o **operador ternário**.

---

# Operador ternário

O operador ternário permite simplificar condições `if/else` quando temos uma situação simples em que precisamos escolher entre **dois valores**.

Ele é chamado de **ternário** porque possui três partes:

```text
condição ? valor_se_verdadeiro : valor_se_falso
```

A estrutura é:

```java
condicao ? valorSeVerdadeiro : valorSeFalso;
```

Temos:

1. **Condição**
2. `?` — valor caso a condição seja verdadeira
3. `:` — valor caso a condição seja falsa

---

# Utilizando o operador ternário

Podemos transformar nosso exemplo anterior em:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : mensagemNaoDoar;
```

Agora podemos imprimir:

```java
System.out.println(resultado);
```

O código completo fica:

```java
public class Aula5EstruturasCondicionais03 {
    public static void main(String[] args) {

        int salario = 6000;

        String mensagemDoar = "Eu vou doar R$ 500,00 para o DevDojo";
        String mensagemNaoDoar = "Eu ainda não tenho condições de doar para o DevDojo";

        String resultado = salario > 5000
                ? mensagemDoar
                : mensagemNaoDoar;

        System.out.println(resultado);
    }
}
```

Se o salário for `6000`, a condição:

```java
salario > 5000
```

será verdadeira.

Portanto, será utilizada:

```java
mensagemDoar
```

Se o salário for `3000`, a condição será falsa e será utilizada:

```java
mensagemNaoDoar
```

---

# O tipo dos valores precisa ser compatível

Como o operador ternário está escolhendo um valor para ser atribuído a uma variável, os valores envolvidos precisam ser compatíveis.

Por exemplo:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : mensagemNaoDoar;
```

Aqui temos:

```java
mensagemDoar
```

e:

```java
mensagemNaoDoar
```

Ambas são do tipo `String`.

Portanto, o resultado também será uma `String`.

Não faria sentido fazer algo como:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : 0;
```

Nesse caso, temos uma `String` de um lado e um `int` do outro.

Por outro lado, se utilizarmos:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : "0";
```

Agora temos `String` nos dois lados:

```java
mensagemDoar
```

e:

```java
"0"
```

Portanto, o resultado é compatível com uma variável `String`.

---

# O operador ternário é uma expressão

Uma característica importante do operador ternário é que ele é uma **expressão**.

Isso significa que podemos utilizar diretamente o resultado da expressão em outros lugares.

Por exemplo:

```java
System.out.println(
        salario > 5000
                ? mensagemDoar
                : mensagemNaoDoar
);
```

Nesse caso, não precisamos nem mesmo criar a variável `resultado`.

O Java avalia a condição e utiliza o valor correspondente dentro do `System.out.println()`.

---

# Simplificando o código

Nosso código anterior:

```java
String resultado;

if (salario > 5000) {
    resultado = mensagemDoar;
} else {
    resultado = mensagemNaoDoar;
}

System.out.println(resultado);
```

Pode ser simplificado para:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : mensagemNaoDoar;

System.out.println(resultado);
```

Ou ainda:

```java
System.out.println(
        salario > 5000
                ? mensagemDoar
                : mensagemNaoDoar
);
```

Tudo depende de como você está desenvolvendo e, principalmente, da **legibilidade do código**.

---

# Operador ternário com `boolean`

O operador ternário também pode trabalhar com valores booleanos.

Por exemplo:

```java
boolean possoDoar = salario > 5000;
```

Aqui estamos verificando se o salário é maior que `5000`.

Se for maior, `possoDoar` será:

```java
true
```

Caso contrário:

```java
false
```

Também poderíamos utilizar o operador ternário:

```java
boolean possoDoar = salario > 5000 ? true : false;
```

Porém, existe um detalhe importante.

Essa segunda forma é **desnecessária**, porque:

```java
salario > 5000
```

já é uma expressão booleana.

Portanto, basta fazer:

```java
boolean possoDoar = salario > 5000;
```

Isso é muito mais simples e legível.

---

# Operador ternário aninhado

Existe ainda uma possibilidade mais complexa: utilizar um operador ternário dentro de outro operador ternário.

É possível fazer isso, mas **não é recomendado** quando o código começa a ficar difícil de entender.

Imagine que queremos determinar uma categoria de acordo com a idade:

* Menor de 15 anos → `Infantil`
* Menor de 18 anos → `Juvenil`
* 18 anos ou mais → `Adulto`

Poderíamos escrever:

```java
String categoria = idade < 15
        ? "Infantil"
        : idade < 18
            ? "Juvenil"
            : "Adulto";
```

Aqui temos um operador ternário dentro de outro.

A lógica seria:

```text
idade < 15?
    ├── Sim → Infantil
    └── Não → verifica outra condição
                    │
                    ├── idade < 18 → Juvenil
                    └── caso contrário → Adulto
```

Por exemplo:

```java
int idade = 20;

String categoria = idade < 15
        ? "Infantil"
        : idade < 18
            ? "Juvenil"
            : "Adulto";

System.out.println(categoria);
```

Resultado:

```text
Adulto
```

Se tivermos:

```java
int idade = 12;
```

Resultado:

```text
Infantil
```

E:

```java
int idade = 16;
```

Resultado:

```text
Juvenil
```

---

# Evite ternários muito complexos

Apesar de ser possível criar vários operadores ternários dentro de outros, isso pode tornar o código extremamente difícil de ler.

Por exemplo:

```java
String categoria = idade < 15
        ? "Infantil"
        : idade < 18
            ? "Juvenil"
            : idade < 60
                ? "Adulto"
                : "Idoso";
```

O código funciona, mas pode ficar difícil de entender e manter.

Nesse caso, um `if/else if/else` provavelmente seria uma escolha melhor:

```java
String categoria;

if (idade < 15) {
    categoria = "Infantil";
} else if (idade < 18) {
    categoria = "Juvenil";
} else if (idade < 60) {
    categoria = "Adulto";
} else {
    categoria = "Idoso";
}
```

A regra é simples:

> **Uma coisa ser possível não significa que ela seja recomendada.**

---

# Quando utilizar o operador ternário?

O operador ternário é mais indicado quando temos uma condição **simples**, em que precisamos escolher entre dois valores.

Por exemplo:

```java
String resultado = salario > 5000
        ? "Posso doar"
        : "Não posso doar";
```

Ou:

```java
int maior = numero1 > numero2
        ? numero1
        : numero2;
```

Ou:

```java
boolean maiorDeIdade = idade >= 18;
```

O objetivo é deixar o código mais simples e direto.

---

# Quando evitar?

Se a condição começar a ficar muito complexa ou envolver vários níveis de decisão, prefira utilizar `if/else`.

Evite:

```java
String resultado = condicao1
        ? valor1
        : condicao2
            ? valor2
            : condicao3
                ? valor3
                : valor4;
```

Nesse caso, provavelmente um `if/else if/else` será mais fácil de entender.

---

# Resumo

O operador ternário possui a seguinte estrutura:

```java
condicao ? valorSeVerdadeiro : valorSeFalso;
```

Ele possui três partes:

```text
condição
   ↓
condicao ? valorSeVerdadeiro : valorSeFalso
             ↑                  ↑
          verdadeiro          falso
```

Um exemplo simples:

```java
String resultado = salario > 5000
        ? "Posso doar"
        : "Não posso doar";
```

É equivalente a:

```java
String resultado;

if (salario > 5000) {
    resultado = "Posso doar";
} else {
    resultado = "Não posso doar";
}
```

Portanto, o operador ternário deve ser utilizado principalmente em situações onde temos um `if/else` **simples**, tornando o código mais compacto sem prejudicar sua legibilidade.

Já os ternários aninhados são possíveis, mas devem ser evitados quando tornam o código difícil de compreender.

---

## Conclusão

E era isso que eu tinha para falar com vocês na aula de hoje sobre o **operador ternário**.

Lembre-se:

> **O operador ternário deve ser utilizado quando temos uma condição simples e precisamos escolher entre dois valores.**

Até a próxima! 🚀
