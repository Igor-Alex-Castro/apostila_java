# Aula 5 — Estruturas Condicionais 03: Operador Ternário

Fala, galera! Sejam todos muito bem-vindos a mais uma aula do curso **Maratona Java**.

Muito obrigado a todos vocês que fazem parte do nosso canal. Vocês são especiais e moram no meu coração. ❤️

Hoje vamos falar sobre o **operador ternário**, que foi criado no Java para simplificar algumas condições, principalmente quando precisamos associar diretamente o resultado de uma condição a uma variável.

---

## Como funciona na prática?

Vamos criar uma nova classe.

Essa será a:

**Aula 5 — Estruturas Condicionais 03**

E vamos utilizar o `PSVM` para criar o método `main`.

Hoje vamos começar com um problema simples.

Quero decidir, por exemplo, se vou fazer uma **doação de R$ 500,00 para o DevDojo**.

Porém, só posso fazer essa doação se o meu salário for **maior que R$ 5.000,00**.

Então vamos começar criando uma variável chamada `salario`:

```java
int salario = 6000;
```

Agora quero criar duas mensagens:

```java
String mensagemDoar = "Eu vou doar R$ 500,00 para o DevDojo";
String mensagemNaoDoar = "Eu ainda não tenho condições de doar para o DevDojo";
```

Temos, portanto, duas possibilidades:

* Se o salário for maior que `5000`, vamos utilizar a mensagem de doação.
* Caso contrário, vamos utilizar a mensagem informando que ainda não temos condições.

---

# Fazendo da maneira tradicional

Primeiro vamos fazer isso da maneira que já conhecemos, utilizando `if/else`.

Vamos criar uma variável chamada `resultado`:

```java
String resultado;
```

Agora fazemos a condição:

```java
if (salario > 5000) {
    resultado = mensagemDoar;
} else {
    resultado = mensagemNaoDoar;
}
```

E podemos imprimir o resultado:

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

        String resultado;

        if (salario > 5000) {
            resultado = mensagemDoar;
        } else {
            resultado = mensagemNaoDoar;
        }

        System.out.println(resultado);
    }
}
```

Como o salário é `6000`, a condição:

```java
salario > 5000
```

é verdadeira.

Portanto, o resultado será:

```text
Eu vou doar R$ 500,00 para o DevDojo
```

Agora, se alterarmos o salário:

```java
int salario = 3000;
```

A condição será falsa e teremos:

```text
Eu ainda não tenho condições de doar para o DevDojo
```

Como vocês podem perceber, é algo simples.

Estamos apenas verificando uma condição e escolhendo qual mensagem será armazenada na variável `resultado`.

E é justamente nesse caso que podemos utilizar o **operador ternário**.

---

# Operador ternário

O operador ternário sempre será utilizado quando queremos obter um resultado a partir de uma condição e associá-lo diretamente a uma variável ou utilizar esse resultado como retorno de um método.

O operador ternário possui **três partes**.

Sua sintaxe é:

```java
condicao ? valorSeVerdadeiro : valorSeFalso;
```

Podemos visualizar da seguinte forma:

```text
condição ? caso_verdadeiro : caso_falso
```

Temos:

1. A **condição**
2. O operador `?`
3. O valor caso a condição seja **verdadeira**
4. O operador `:`
5. O valor caso a condição seja **falsa**

---

# Utilizando o operador ternário

No nosso exemplo, a condição é:

```java
salario > 5000
```

Se for verdadeira, queremos utilizar:

```java
mensagemDoar
```

Se for falsa, queremos utilizar:

```java
mensagemNaoDoar
```

Então podemos substituir todo o `if/else` por:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : mensagemNaoDoar;
```

Agora basta imprimir:

```java
System.out.println(resultado);
```

Nosso código fica muito mais simples:

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

Se o salário for `6000`:

```text
Eu vou doar R$ 500,00 para o DevDojo
```

Se o salário for `3000`:

```text
Eu ainda não tenho condições de doar para o DevDojo
```

---

# O tipo precisa ser compatível

Como o operador ternário está associando um valor diretamente a uma variável, os valores envolvidos precisam ser compatíveis.

Por exemplo:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : mensagemNaoDoar;
```

Nesse caso, tanto `mensagemDoar` quanto `mensagemNaoDoar` são `String`.

Portanto, o resultado também será uma `String`.

Não podemos simplesmente fazer:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : 0;
```

Aqui temos:

```java
mensagemDoar // String
```

e:

```java
0 // int
```

Os tipos são diferentes e isso pode gerar um problema de compatibilidade.

Se colocarmos o `0` entre aspas:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : "0";
```

Agora `"0"` também é uma `String`.

Ou seja, estamos sempre associando um valor ao resultado da expressão.

---

# O operador ternário é uma expressão

Uma característica importante do operador ternário é que ele é uma **expressão válida**.

Isso significa que não precisamos necessariamente atribuí-lo a uma variável.

Podemos utilizar diretamente dentro de um `System.out.println()`:

```java
System.out.println(
        salario > 5000
                ? mensagemDoar
                : mensagemNaoDoar
);
```

Nesse caso, o resultado da expressão será utilizado diretamente pelo `System.out.println()`.

Se o salário for `3000`, teremos:

```text
Eu ainda não tenho condições de doar para o DevDojo
```

Se alterarmos para:

```java
int salario = 6000;
```

teremos:

```text
Eu vou doar R$ 500,00 para o DevDojo
```

---

# Simplificando ainda mais

Podemos deixar nosso programa ainda mais limpo.

Em vez de criar as duas mensagens, criar uma variável `resultado` e depois imprimir, podemos fazer tudo diretamente:

```java
System.out.println(
        salario > 5000
                ? "Eu vou doar R$ 500,00 para o DevDojo"
                : "Eu ainda não tenho condições de doar para o DevDojo"
);
```

Isso depende da forma como você está desenvolvendo.

Às vezes, criar uma variável deixa o código mais fácil de entender. Em outras situações, utilizar diretamente a expressão deixa o código mais limpo.

O importante é sempre pensar na **legibilidade**.

---

# Operador ternário com `boolean`

Também podemos utilizar o operador ternário com valores booleanos.

Por exemplo, podemos ter:

```java
boolean possoDoar = salario > 5000;
```

Nesse caso:

* Se `salario > 5000` for verdadeiro, `possoDoar` será `true`.
* Caso contrário, será `false`.

Também seria possível escrever:

```java
boolean possoDoar = salario > 5000 ? true : false;
```

Porém, isso é desnecessário.

A própria expressão:

```java
salario > 5000
```

já retorna um valor booleano.

Portanto, é muito melhor simplesmente fazer:

```java
boolean possoDoar = salario > 5000;
```

Ou seja:

> Nem tudo que podemos fazer com o operador ternário significa que devemos fazer.

---

# Operador ternário aninhado

Existe ainda uma forma mais complexa de utilizar o operador ternário.

Podemos colocar um operador ternário dentro de outro.

Isso é possível, mas **não é recomendado** para código de produção quando a expressão fica difícil de entender.

Por exemplo, imagine que queremos determinar uma categoria de acordo com a idade:

* Menor de 15 anos → `Infantil`
* Menor de 18 anos → `Juvenil`
* 18 anos ou mais → `Adulto`

Com `if/else`, poderíamos fazer:

```java
String categoria;

if (idade < 15) {
    categoria = "Infantil";
} else if (idade < 18) {
    categoria = "Juvenil";
} else {
    categoria = "Adulto";
}
```

Podemos representar a mesma lógica utilizando operadores ternários:

```java
String categoria = idade < 15
        ? "Infantil"
        : idade < 18
                ? "Juvenil"
                : "Adulto";
```

Observe que, quando a primeira condição é falsa, iniciamos um **novo operador ternário**:

```java
idade < 18
        ? "Juvenil"
        : "Adulto"
```

---

# Exemplo completo

```java
public class Aula5EstruturasCondicionais03 {
    public static void main(String[] args) {

        int idade = 20;

        String categoria = idade < 15
                ? "Infantil"
                : idade < 18
                        ? "Juvenil"
                        : "Adulto";

        System.out.println(categoria);
    }
}
```

Como a idade é `20`, a primeira condição:

```java
idade < 15
```

é falsa.

Então verificamos a segunda:

```java
idade < 18
```

Também é falsa.

Portanto, chegamos ao último valor:

```java
"Adulto"
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

Se tivermos:

```java
int idade = 16;
```

Resultado:

```text
Juvenil
```

---

# Por que evitar ternários aninhados?

Apesar de funcionar, esse tipo de código pode ficar extremamente complicado e difícil de ler.

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

Imagine ter várias condições desse tipo no meio de um código grande.

Provavelmente outro desenvolvedor terá dificuldade para entender o que está acontecendo.

Por isso, quando temos várias condições, normalmente é melhor utilizar `if/else if/else`:

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

Esse código é mais extenso, mas é muito mais fácil de ler.

---

# Possível não significa recomendado

Essa é uma ideia importante para guardar:

> **Uma coisa ser possível não significa que ela seja recomendada.**

Você pode colocar um operador ternário dentro de outro operador ternário.

Pode colocar vários.

Mas isso não significa que você deva fazer isso no seu código.

Se você possui um `if/else` simples, o operador ternário pode deixar o código mais limpo.

Se possui muitas condições, provavelmente o `if/else` será uma opção melhor.

---

# Quando utilizar o operador ternário?

O operador ternário é recomendado principalmente quando temos uma condição simples com **dois possíveis resultados**.

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

Ou simplesmente:

```java
boolean possoDoar = salario > 5000;
```

O objetivo é tornar o código mais simples e direto.

---

# Quando utilizar `if/else`?

Quando temos várias condições ou uma lógica mais complexa, prefira `if/else`.

Por exemplo:

```java
if (idade < 15) {
    categoria = "Infantil";
} else if (idade < 18) {
    categoria = "Juvenil";
} else {
    categoria = "Adulto";
}
```

Nesse caso, utilizar vários operadores ternários deixaria o código mais difícil de compreender.

---

# Resumo

A sintaxe do operador ternário é:

```java
condicao ? valorSeVerdadeiro : valorSeFalso;
```

Ele possui três partes:

```text
             condição
                 ↓
        salario > 5000
              /     \
           true     false
            ↓         ↓
    mensagemDoar  mensagemNaoDoar
```

Exemplo:

```java
String resultado = salario > 5000
        ? mensagemDoar
        : mensagemNaoDoar;
```

Isso é equivalente a:

```java
String resultado;

if (salario > 5000) {
    resultado = mensagemDoar;
} else {
    resultado = mensagemNaoDoar;
}
```

A principal diferença é que o operador ternário permite escrever essa lógica de forma mais compacta.

---

# Conclusão

O **operador ternário** deve ser utilizado principalmente em situações onde temos um `if/else` simples e precisamos escolher entre dois valores.

Ele pode ser utilizado diretamente em uma atribuição:

```java
String resultado = condicao
        ? valorVerdadeiro
        : valorFalso;
```

Ou diretamente como expressão:

```java
System.out.println(
        condicao
                ? valorVerdadeiro
                : valorFalso
);
```

Também é possível utilizar operadores ternários dentro de outros operadores ternários, mas isso deve ser evitado quando prejudicar a legibilidade do código.

Lembre-se:

> **Poder fazer uma coisa não significa que você deve fazer.**

Se temos um `if/else` simples, o operador ternário pode ser uma ótima escolha.

Se temos várias condições ou uma lógica mais complexa, o `if/else` provavelmente será mais adequado.

E era isso que eu tinha para falar com vocês na aula de hoje sobre o **operador ternário**.

Até a próxima! 🚀
