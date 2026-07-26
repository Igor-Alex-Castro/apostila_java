# Estruturas Condicionais em Java — `if`

## Introdução

Nesta aula, vamos começar um dos conceitos mais importantes da programação: as **estruturas condicionais**.

As estruturas condicionais permitem que o programa tome decisões, executando diferentes blocos de código dependendo de uma determinada condição.

No dia a dia, utilizamos condições o tempo todo:

* Se não vier carro, vou atravessar a rua.
* Se eu tiver dinheiro, vou comprar comida.
* Se eu tiver dinheiro suficiente, vou comprar um PlayStation 5.
* Se eu tiver condições, vou procurar um trabalho.

Na programação, essa mesma lógica é utilizada para controlar o comportamento do sistema.

Uma das estruturas condicionais mais utilizadas em Java é o `if`.

---

# Criando uma Classe para a Aula

Para criar uma nova classe no IntelliJ IDEA:

1. Clique com o botão direito no pacote.
2. Selecione **New**.
3. Escolha **Java Class**.
4. Informe o nome da classe.

Para esta aula, podemos utilizar:

```text
Aula09EstruturasCondicionais
```

A estrutura básica será:

```java
public class Aula09EstruturasCondicionais {

    public static void main(String[] args) {

    }

}
```

O método `main` é o ponto de entrada da aplicação Java.

---

# Estrutura Condicional `if`

A palavra `if` significa **"se"**.

A estrutura básica é:

```java
if (condicao) {

}
```

Dentro dos parênteses, devemos colocar uma expressão que obrigatoriamente resulte em um valor booleano:

```java
true
```

ou:

```java
false
```

Exemplo:

```java
if (true) {
    System.out.println("Dentro do IF");
}
```

Como a condição é `true`, o código dentro do `if` será executado.

Saída:

```text
Dentro do IF
```

---

# Como o `if` Funciona?

O `if` executa o bloco de código somente quando a condição for verdadeira.

Exemplo:

```java
if (true) {
    System.out.println("Dentro do IF");
}

System.out.println("Fora do IF");
```

Resultado:

```text
Dentro do IF
Fora do IF
```

O programa executa o código de cima para baixo.

Primeiro:

```java
System.out.println("Dentro do IF");
```

Depois:

```java
System.out.println("Fora do IF");
```

Agora, se a condição for `false`:

```java
if (false) {
    System.out.println("Dentro do IF");
}

System.out.println("Fora do IF");
```

Resultado:

```text
Fora do IF
```

Isso acontece porque o bloco do `if` só é executado quando sua condição é verdadeira.

---

# Bloco de Código do `if`

A forma mais comum de utilizar o `if` é com um bloco delimitado por chaves:

```java
if (condicao) {
    // código executado se a condição for verdadeira
}
```

Exemplo:

```java
if (true) {
    System.out.println("A condição é verdadeira");
}
```

As chaves `{}` definem o bloco de código que pertence ao `if`.

---

# `if` Sem Chaves

Em Java, quando existe apenas uma instrução dentro do `if`, é possível omitir as chaves.

Exemplo:

```java
if (true)
    System.out.println("Dentro do IF");
```

Esse código funciona normalmente.

Porém, essa prática **não é recomendada**.

Prefira sempre utilizar as chaves:

```java
if (true) {
    System.out.println("Dentro do IF");
}
```

Isso deixa o código mais claro e evita confusão, principalmente quando o código crescer.

Além disso, muitas empresas utilizam ferramentas de formatação automática que padronizam o uso das chaves.

---

# Exemplo com Variável

Podemos utilizar variáveis para criar condições.

Imagine que temos a idade de uma pessoa:

```java
int idade = 20;
```

Agora queremos verificar se essa pessoa possui idade suficiente para comprar bebida alcoólica.

Podemos criar a seguinte condição:

```java
if (idade >= 18) {
    System.out.println("Autorizado a comprar bebida alcoólica");
}
```

Nesse exemplo, temos:

```java
idade >= 18
```

Essa expressão retorna um valor booleano.

Se:

```java
idade = 20;
```

A condição será:

```text
20 >= 18
```

Resultado:

```text
true
```

Portanto, o código dentro do `if` será executado.

Saída:

```text
Autorizado a comprar bebida alcoólica
```

---

# Quando a Condição é Falsa

Agora imagine:

```java
int idade = 15;
```

E:

```java
if (idade >= 18) {
    System.out.println("Autorizado a comprar bebida alcoólica");
}
```

A condição será:

```text
15 >= 18
```

Resultado:

```text
false
```

Como a condição é falsa, o código dentro do `if` não será executado.

---

# Criando uma Variável `boolean`

Também podemos armazenar o resultado da condição em uma variável booleana.

Exemplo:

```java
int idade = 20;

boolean autorizado = idade >= 18;
```

Nesse caso, a expressão:

```java
idade >= 18
```

será avaliada primeiro.

Como:

```text
20 >= 18
```

é verdadeiro, teremos:

```java
boolean autorizado = true;
```

Podemos então utilizar essa variável no `if`:

```java
if (autorizado) {
    System.out.println("Autorizado a comprar bebida alcoólica");
}
```

Essa é uma forma bastante comum de trabalhar com condições booleanas.

---

# Comparando `boolean` com `false`

Também é possível verificar explicitamente se uma variável booleana é `false`.

Exemplo:

```java
boolean autorizado = false;

if (autorizado == false) {
    System.out.println("Não autorizado a comprar bebida alcoólica");
}
```

Nesse caso:

```java
autorizado == false
```

significa:

> O valor de `autorizado` é igual a `false`?

Como a variável contém `false`, o resultado da comparação será:

```text
true
```

Portanto, o código será executado.

---

# Operador de Negação `!`

Existe uma maneira mais simples e mais comum de verificar se um valor booleano é falso.

Para isso, utilizamos o operador de negação:

```java
!
```

O operador `!` inverte o valor booleano.

| Valor   | Negação |
| ------- | ------- |
| `true`  | `false` |
| `false` | `true`  |

Exemplo:

```java
boolean autorizado = false;

if (!autorizado) {
    System.out.println("Não autorizado a comprar bebida alcoólica");
}
```

Podemos interpretar:

```java
!autorizado
```

como:

> "Se não está autorizado..."

Como `autorizado` é `false`, a negação transforma o resultado em `true`.

Portanto, a mensagem será exibida.

---

# `== false` ou `!`

As duas formas abaixo possuem o mesmo efeito:

```java
if (autorizado == false) {
    System.out.println("Não autorizado");
}
```

E:

```java
if (!autorizado) {
    System.out.println("Não autorizado");
}
```

Porém, normalmente preferimos utilizar:

```java
if (!autorizado) {
    System.out.println("Não autorizado");
}
```

Essa forma é mais simples e mais idiomática em Java.

Podemos ler:

```java
if (!autorizado)
```

como:

> Se não estiver autorizado.

---

# A Condição do `if` Deve Ser `boolean`

Um ponto muito importante é que o `if` precisa receber uma expressão que resulte em:

```java
true
```

ou:

```java
false
```

Por exemplo:

```java
int idade = 20;

if (idade >= 18) {
    System.out.println("Maior de idade");
}
```

A expressão:

```java
idade >= 18
```

retorna um `boolean`.

Portanto, funciona corretamente.

---

# Exemplo Incorreto

Não podemos colocar diretamente um `int` dentro do `if`:

```java
int idade = 20;

if (idade) {
    System.out.println("Maior de idade");
}
```

Esse código gera erro de compilação.

Isso acontece porque:

```java
idade
```

é um `int`, e não um `boolean`.

Java não interpreta automaticamente:

```text
0 = false
1 = true
```

como acontece em algumas outras linguagens.

No Java, o `if` precisa receber explicitamente uma expressão booleana.

---

# Cuidado com o Operador `=`

Outro ponto importante é diferenciar:

```java
=
```

de:

```java
==
```

O operador `=` é utilizado para **atribuição**.

Exemplo:

```java
boolean autorizado = false;
```

Aqui estamos atribuindo `false` à variável.

Já o operador `==` é utilizado para **comparação**.

Exemplo:

```java
if (autorizado == false) {
    System.out.println("Não autorizado");
}
```

Nesse caso, estamos verificando se `autorizado` é igual a `false`.

---

# Atribuição Dentro do `if`

É possível utilizar uma atribuição dentro da condição em algumas situações, mas isso geralmente não é recomendado e pode causar confusão.

Por exemplo:

```java
boolean autorizado = false;

if (autorizado = true) {
    System.out.println("Autorizado");
}
```

Nesse código:

```java
autorizado = true
```

é uma atribuição, não uma comparação.

A variável `autorizado` recebe `true` antes da avaliação da condição.

O resultado é que o `if` será executado.

Porém, esse código não representa uma boa prática.

Se a intenção é verificar se a variável é verdadeira, basta fazer:

```java
if (autorizado) {
    System.out.println("Autorizado");
}
```

Se a intenção é verificar se é falsa:

```java
if (!autorizado) {
    System.out.println("Não autorizado");
}
```

---

# Exemplo Completo

```java
public class Aula09EstruturasCondicionais {

    public static void main(String[] args) {

        int idade = 20;

        if (idade >= 18) {
            System.out.println("Autorizado a comprar bebida alcoólica");
        }

        boolean autorizado = idade >= 18;

        if (autorizado) {
            System.out.println("Usuário autorizado");
        }

        if (!autorizado) {
            System.out.println("Usuário não autorizado");
        }
    }

}
```

---

# Fluxo de Execução

Considerando:

```java
int idade = 20;
```

A primeira condição:

```java
if (idade >= 18)
```

será avaliada como:

```text
20 >= 18
```

Resultado:

```text
true
```

O bloco será executado.

Depois:

```java
boolean autorizado = idade >= 18;
```

O resultado será:

```java
autorizado = true;
```

Então:

```java
if (autorizado)
```

será verdadeiro.

Já:

```java
if (!autorizado)
```

será falso, porque:

```java
!true
```

resulta em:

```java
false
```

Portanto, esse último bloco não será executado.

---

# Resumo

Nesta aula aprendemos:

* ✅ O que são estruturas condicionais.
* ✅ Como utilizar o `if`.
* ✅ O `if` significa "se".
* ✅ A condição do `if` deve resultar em `true` ou `false`.
* ✅ Como utilizar blocos de código com `{}`.
* ✅ É possível omitir as chaves quando existe apenas uma instrução, mas isso não é recomendado.
* ✅ Como utilizar comparações dentro do `if`.
* ✅ Como utilizar variáveis do tipo `boolean`.
* ✅ A diferença entre `=` e `==`.
* ✅ O operador de negação `!`.
* ✅ A diferença entre `autorizado == false` e `!autorizado`.
* ✅ Um `int` não pode ser utilizado diretamente como condição de um `if`.
* ✅ A atribuição `=` não deve ser confundida com a comparação `==`.

---

# Conceitos Principais

A estrutura básica do `if` é:

```java
if (condicao) {
    // código executado se a condição for verdadeira
}
```

Uma condição pode ser uma comparação:

```java
if (idade >= 18) {
    System.out.println("Maior de idade");
}
```

Ou uma variável booleana:

```java
boolean autorizado = true;

if (autorizado) {
    System.out.println("Autorizado");
}
```

Para verificar uma condição negada:

```java
if (!autorizado) {
    System.out.println("Não autorizado");
}
```

O `if` será executado **somente quando a condição resultar em `true`**.
