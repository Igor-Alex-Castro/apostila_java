# Aula 5 — Estruturas Condicionais 06: Switch Statement

## Introdução

Fala, galera! Sejam todos muito bem-vindos novamente ao curso **Maratona Java**.

Muito obrigado a todos vocês que são membros do nosso canal. Vocês são especiais! ❤️

Na aula de hoje vamos falar sobre o **Switch Statement**.

O `switch` é uma funcionalidade do Java que permite organizar melhor determinadas condições quando precisamos fazer uma escolha simples baseada no valor de uma variável.

---

# O que é o `switch`?

O `switch` é uma estrutura de controle que pode ser utilizada quando temos uma variável e queremos executar diferentes blocos de código dependendo do valor dessa variável.

Por exemplo, imagine que queremos descobrir o dia da semana com base em um número:

```text
1 → Domingo
2 → Segunda-feira
3 → Terça-feira
4 → Quarta-feira
5 → Quinta-feira
6 → Sexta-feira
7 → Sábado
```

Poderíamos fazer isso utilizando vários `if/else if`.

Porém, o código ficaria grande:

```java
if (dia == 1) {
    System.out.println("Domingo");
} else if (dia == 2) {
    System.out.println("Segunda-feira");
} else if (dia == 3) {
    System.out.println("Terça-feira");
}
```

E assim por diante até o dia `7`.

Para esse tipo de situação, o `switch` pode deixar o código mais organizado e fácil de visualizar.

---

# Criando a classe

Vamos criar uma nova classe chamada:

```text
Aula5EstruturasCondicionais06
```

E vamos utilizar o método `main`:

```java
public static void main(String[] args) {

}
```

---

# Exemplo com dias da semana

Vamos começar criando uma variável para armazenar o dia:

```java
int dia = 5;
```

Agora podemos utilizar o `switch`:

```java
switch (dia) {

}
```

A estrutura básica do `switch` é:

```java
switch (variavel) {
    case valor:
        // código
        break;
}
```

---

# `case`

Dentro do `switch`, utilizamos o `case` para definir quais valores queremos verificar.

Por exemplo:

```java
switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;
}
```

Nesse caso, estamos dizendo:

> Se `dia` for igual a `1`, execute o código desse `case`.

Podemos adicionar vários `case`:

```java
switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;

    case 2:
        System.out.println("Segunda-feira");
        break;

    case 3:
        System.out.println("Terça-feira");
        break;

    case 4:
        System.out.println("Quarta-feira");
        break;

    case 5:
        System.out.println("Quinta-feira");
        break;

    case 6:
        System.out.println("Sexta-feira");
        break;

    case 7:
        System.out.println("Sábado");
        break;
}
```

Agora temos uma estrutura muito mais organizada.

---

# Como o `switch` funciona?

Imagine que temos:

```java
int dia = 5;
```

E:

```java
switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;

    case 2:
        System.out.println("Segunda-feira");
        break;

    case 3:
        System.out.println("Terça-feira");
        break;

    case 4:
        System.out.println("Quarta-feira");
        break;

    case 5:
        System.out.println("Quinta-feira");
        break;

    case 6:
        System.out.println("Sexta-feira");
        break;

    case 7:
        System.out.println("Sábado");
        break;
}
```

O Java verifica o valor de `dia`.

Como:

```java
dia = 5;
```

ele procura:

```text
case 1 → não
case 2 → não
case 3 → não
case 4 → não
case 5 → sim
```

Quando encontra o `case` correspondente, executa o código daquele bloco.

Resultado:

```text
Quinta-feira
```

---

# O `break`

O `break` é extremamente importante quando utilizamos o `switch` dessa forma.

Ele serve para **interromper a execução do `switch`**.

Por exemplo:

```java
case 5:
    System.out.println("Quinta-feira");
    break;
```

Quando o Java encontra o `case 5`, ele executa:

```java
System.out.println("Quinta-feira");
```

Depois encontra:

```java
break;
```

e sai do `switch`.

---

# O que acontece sem o `break`?

Esse é um detalhe muito importante.

Imagine que tenhamos:

```java
switch (dia) {
    case 5:
        System.out.println("Quinta-feira");

    case 6:
        System.out.println("Sexta-feira");

    case 7:
        System.out.println("Sábado");
}
```

E:

```java
int dia = 5;
```

O Java encontra o `case 5` e começa a executar.

Porém, como não existe um `break`, ele continua executando os próximos `case`.

O resultado será:

```text
Quinta-feira
Sexta-feira
Sábado
```

Isso acontece porque, depois que o Java encontra um `case` correspondente, ele continua a execução dos próximos blocos até encontrar um `break` ou chegar ao final do `switch`.

Esse comportamento é chamado de **fall-through**.

---

# Utilizando `break`

Normalmente queremos executar somente o código correspondente ao valor encontrado.

Por isso, utilizamos:

```java
switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;

    case 2:
        System.out.println("Segunda-feira");
        break;

    case 3:
        System.out.println("Terça-feira");
        break;

    case 4:
        System.out.println("Quarta-feira");
        break;

    case 5:
        System.out.println("Quinta-feira");
        break;

    case 6:
        System.out.println("Sexta-feira");
        break;

    case 7:
        System.out.println("Sábado");
        break;
}
```

Assim, quando encontrar o `case` correto, o Java executa o código e sai do `switch`.

---

# `default`

Agora imagine que o usuário informe um valor inválido.

Por exemplo:

```java
int dia = 10;
```

Mas temos apenas:

```text
1 → Domingo
2 → Segunda-feira
3 → Terça-feira
4 → Quarta-feira
5 → Quinta-feira
6 → Sexta-feira
7 → Sábado
```

O que acontece?

Nenhum dos `case` será encontrado.

Nesse caso, podemos utilizar o `default`.

O `default` funciona como uma opção padrão quando nenhum `case` corresponde ao valor informado.

Exemplo:

```java
switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;

    case 2:
        System.out.println("Segunda-feira");
        break;

    case 3:
        System.out.println("Terça-feira");
        break;

    case 4:
        System.out.println("Quarta-feira");
        break;

    case 5:
        System.out.println("Quinta-feira");
        break;

    case 6:
        System.out.println("Sexta-feira");
        break;

    case 7:
        System.out.println("Sábado");
        break;

    default:
        System.out.println("Opção inválida");
}
```

Se:

```java
int dia = 10;
```

o resultado será:

```text
Opção inválida
```

---

# O `default` pode ficar em qualquer lugar

É importante saber que o `default` **não precisa obrigatoriamente ser o último bloco** do `switch`.

Ele pode aparecer em outra posição.

Porém, quando estamos utilizando o `switch` tradicional com `break`, normalmente colocamos o `default` no final porque isso facilita a leitura do código.

Por exemplo:

```java
switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;

    case 2:
        System.out.println("Segunda-feira");
        break;

    default:
        System.out.println("Opção inválida");
        break;
}
```

---

# Cuidado com o `break` no `default`

O `default` também pode precisar de `break`, dependendo da posição em que ele estiver e da forma como o `switch` foi escrito.

Por exemplo:

```java
default:
    System.out.println("Opção inválida");
    break;
```

Se o `default` estiver no final, o `break` não é necessário para impedir a execução de um `case` posterior, porque não existe outro `case` depois dele.

Mesmo assim, é importante entender o comportamento do `break` e do **fall-through**.

---

# Exemplo completo — Dias da semana

```java
public class Aula5EstruturasCondicionais06 {
    public static void main(String[] args) {

        int dia = 5;

        switch (dia) {
            case 1:
                System.out.println("Domingo");
                break;

            case 2:
                System.out.println("Segunda-feira");
                break;

            case 3:
                System.out.println("Terça-feira");
                break;

            case 4:
                System.out.println("Quarta-feira");
                break;

            case 5:
                System.out.println("Quinta-feira");
                break;

            case 6:
                System.out.println("Sexta-feira");
                break;

            case 7:
                System.out.println("Sábado");
                break;

            default:
                System.out.println("Opção inválida");
        }
    }
}
```

Com:

```java
int dia = 5;
```

teremos:

```text
Quinta-feira
```

---

# Outro exemplo: sexo

Agora vamos fazer outro exemplo.

Queremos desenvolver um algoritmo que imprima se a pessoa é **homem ou mulher**, com base no sexo informado.

Nesse exemplo, vamos utilizar:

```text
M → Homem
F → Mulher
```

Como estamos trabalhando com apenas uma letra, podemos utilizar uma variável do tipo `char`.

```java
char sexo = 'M';
```

Agora podemos utilizar o `switch`:

```java
switch (sexo) {
    case 'M':
        System.out.println("Homem");
        break;

    case 'F':
        System.out.println("Mulher");
        break;

    default:
        System.out.println("Sexo inválido");
}
```

---

# Exemplo completo

```java
public class Aula5EstruturasCondicionais06 {
    public static void main(String[] args) {

        char sexo = 'M';

        switch (sexo) {
            case 'M':
                System.out.println("Homem");
                break;

            case 'F':
                System.out.println("Mulher");
                break;

            default:
                System.out.println("Sexo inválido");
        }
    }
}
```

Resultado:

```text
Homem
```

Se alterarmos:

```java
char sexo = 'F';
```

teremos:

```text
Mulher
```

E se colocarmos:

```java
char sexo = 'X';
```

teremos:

```text
Sexo inválido
```

---

# `char` e `String`

Quando utilizamos `char`, usamos **aspas simples**:

```java
char sexo = 'M';
```

Já quando utilizamos `String`, usamos **aspas duplas**:

```java
String sexo = "M";
```

Portanto:

```java
'M'
```

é um `char`.

Enquanto:

```java
"M"
```

é uma `String`.

Se estivermos trabalhando com `String`, os `case` também deverão utilizar `String`:

```java
String sexo = "M";

switch (sexo) {
    case "M":
        System.out.println("Homem");
        break;

    case "F":
        System.out.println("Mulher");
        break;

    default:
        System.out.println("Sexo inválido");
}
```

Os tipos precisam ser compatíveis.

---

# Utilizando chaves `{}` dentro do `case`

Também podemos utilizar chaves para criar um bloco de código dentro de um `case`.

Por exemplo:

```java
switch (sexo) {
    case 'M': {
        System.out.println("Homem");
        break;
    }

    case 'F': {
        System.out.println("Mulher");
        break;
    }

    default: {
        System.out.println("Sexo inválido");
    }
}
```

Isso é válido.

Porém, não é comum vermos essa estrutura em códigos simples.

Na maioria dos casos, podemos escrever diretamente:

```java
case 'M':
    System.out.println("Homem");
    break;
```

---

# `switch` x `if/else`

Podemos resolver alguns problemas utilizando tanto `if/else` quanto `switch`.

Por exemplo, com `if/else`:

```java
if (dia == 1) {
    System.out.println("Domingo");
} else if (dia == 2) {
    System.out.println("Segunda-feira");
} else if (dia == 3) {
    System.out.println("Terça-feira");
}
```

Com `switch`:

```java
switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;

    case 2:
        System.out.println("Segunda-feira");
        break;

    case 3:
        System.out.println("Terça-feira");
        break;
}
```

Para esse tipo de situação, o `switch` pode deixar a intenção do código mais clara.

---

# Quando utilizar o `switch`?

O `switch` é especialmente interessante quando temos:

* Uma variável.
* Vários valores possíveis.
* Uma ação diferente para cada valor.

Por exemplo:

```text
dia → 1, 2, 3, 4, 5, 6, 7
```

ou:

```text
sexo → M, F
```

ou:

```text
opção → 1, 2, 3, 4
```

---

# Estrutura básica

A estrutura tradicional do `switch` é:

```java
switch (variavel) {

    case valor1:
        // código
        break;

    case valor2:
        // código
        break;

    case valor3:
        // código
        break;

    default:
        // código padrão
}
```

---

# Resumo

## `switch`

Utilizado para escolher um bloco de código com base no valor de uma expressão.

```java
switch (variavel) {
}
```

## `case`

Representa uma possibilidade:

```java
case 1:
```

## `break`

Interrompe a execução do `switch`:

```java
break;
```

Sem ele, podemos ter **fall-through**, fazendo com que os próximos `case` também sejam executados.

## `default`

É executado quando nenhum `case` corresponde ao valor informado:

```java
default:
    System.out.println("Opção inválida");
```

---

# Fluxo de execução

Podemos imaginar o funcionamento dessa forma:

```text
             switch(dia)
                  |
                  v
          ┌───────────────┐
          │ dia == 1 ?    │── sim ──> Domingo ──> break
          └───────────────┘
                  |
                 não
                  v
          ┌───────────────┐
          │ dia == 2 ?    │── sim ──> Segunda ──> break
          └───────────────┘
                  |
                 não
                  v
                 ...
                  |
                  v
          ┌───────────────┐
          │ nenhum case?  │
          └───────────────┘
                  |
                  v
              default
```

---

# Conclusão

O `switch` é uma estrutura de controle muito útil quando precisamos fazer escolhas simples baseadas no valor de uma variável.

Ele pode tornar o código mais organizado e mais fácil de visualizar do que uma sequência grande de `if/else if`.

A estrutura tradicional é:

```java
switch (variavel) {
    case valor:
        // código
        break;

    default:
        // código padrão
}
```

Os principais pontos que precisamos lembrar são:

```text
switch  → define a expressão que será analisada

case    → define os valores possíveis

break   → interrompe a execução do switch

default → executado quando nenhum case corresponde
```

Também é importante lembrar que, se não utilizarmos `break`, o Java poderá continuar executando os próximos `case`.

E era isso que tínhamos para falar na aula de hoje sobre **Switch Statement**.

Até a próxima! 🚀
