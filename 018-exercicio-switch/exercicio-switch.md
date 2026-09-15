# Aula 5 — Estruturas Condicionais 06: Exercício com Switch

## Exercício

Neste exercício vamos praticar um pouco mais as **estruturas condicionais**, utilizando o `switch`.

O problema é simples:

> Dado um valor de `1` a `7`, imprima se o dia é **dia útil** ou **final de semana**, considerando que `1` representa domingo.

### Regras

| Valor | Dia           | Classificação   |
| ----: | ------------- | --------------- |
|     1 | Domingo       | Final de semana |
|     2 | Segunda-feira | Dia útil        |
|     3 | Terça-feira   | Dia útil        |
|     4 | Quarta-feira  | Dia útil        |
|     5 | Quinta-feira  | Dia útil        |
|     6 | Sexta-feira   | Dia útil        |
|     7 | Sábado        | Final de semana |

---

# Resolução

Podemos utilizar o `switch` para resolver o exercício.

Primeiro, vamos criar uma variável para representar o dia:

```java
int dia = 1;
```

Agora podemos criar o `switch`:

```java
switch (dia) {

}
```

Uma forma tradicional seria criar um `case` para cada dia:

```java
switch (dia) {
    case 1:
        System.out.println("Final de semana");
        break;

    case 2:
        System.out.println("Dia útil");
        break;

    case 3:
        System.out.println("Dia útil");
        break;

    case 4:
        System.out.println("Dia útil");
        break;

    case 5:
        System.out.println("Dia útil");
        break;

    case 6:
        System.out.println("Dia útil");
        break;

    case 7:
        System.out.println("Final de semana");
        break;

    default:
        System.out.println("Opção inválida");
        break;
}
```

Essa solução funciona perfeitamente.

Porém, podemos aproveitar uma característica do `switch` para deixar o código mais simples.

---

# Aproveitando o `fall-through`

Como já vimos na aula anterior, quando não colocamos o `break` em um `case`, o Java continua executando os próximos `case`.

Podemos utilizar esse comportamento a nosso favor.

Sabemos que:

```text
1 → Domingo → Final de semana
7 → Sábado → Final de semana
```

E:

```text
2, 3, 4, 5 e 6 → Dias úteis
```

Então podemos agrupar os `case` que possuem o mesmo resultado.

```java
switch (dia) {
    case 1:
    case 7:
        System.out.println("Final de semana");
        break;

    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
        System.out.println("Dia útil");
        break;

    default:
        System.out.println("Opção inválida");
        break;
}
```

---

# Como isso funciona?

Vamos entender o primeiro grupo:

```java
case 1:
case 7:
    System.out.println("Final de semana");
    break;
```

Quando:

```java
dia = 1;
```

o Java entra no:

```java
case 1:
```

Como não existe um `break` imediatamente depois dele, ele continua para o próximo `case`:

```java
case 7:
```

E então executa:

```java
System.out.println("Final de semana");
```

Depois encontra:

```java
break;
```

e sai do `switch`.

O mesmo acontece quando:

```java
dia = 7;
```

Nesse caso, ele entra diretamente no:

```java
case 7:
```

e imprime:

```text
Final de semana
```

---

# Agrupando os dias úteis

Podemos fazer a mesma coisa com os dias úteis:

```java
case 2:
case 3:
case 4:
case 5:
case 6:
    System.out.println("Dia útil");
    break;
```

Todos esses valores possuem o mesmo comportamento.

Portanto:

```text
2 → Dia útil
3 → Dia útil
4 → Dia útil
5 → Dia útil
6 → Dia útil
```

Não precisamos repetir:

```java
System.out.println("Dia útil");
```

cinco vezes.

---

# Código completo

```java
public class Aula5EstruturasCondicionais06 {
    public static void main(String[] args) {

        int dia = 1;

        switch (dia) {
            case 1:
            case 7:
                System.out.println("Final de semana");
                break;

            case 2:
            case 3:
            case 4:
            case 5:
            case 6:
                System.out.println("Dia útil");
                break;

            default:
                System.out.println("Opção inválida");
                break;
        }
    }
}
```

---

# Testando o programa

## Teste com `1`

```java
int dia = 1;
```

Resultado:

```text
Final de semana
```

---

## Teste com `7`

```java
int dia = 7;
```

Resultado:

```text
Final de semana
```

---

## Teste com `3`

```java
int dia = 3;
```

Resultado:

```text
Dia útil
```

---

## Teste com um valor inválido

Por exemplo:

```java
int dia = 10;
```

Resultado:

```text
Opção inválida
```

---

# O que aprendemos neste exercício?

Este exercício mostra que existem diferentes formas de resolver um mesmo problema.

Uma solução poderia utilizar vários `if/else`:

```java
if (dia == 1 || dia == 7) {
    System.out.println("Final de semana");
} else if (dia >= 2 && dia <= 6) {
    System.out.println("Dia útil");
} else {
    System.out.println("Opção inválida");
}
```

Também podemos utilizar o `switch`:

```java
switch (dia) {
    case 1:
    case 7:
        System.out.println("Final de semana");
        break;

    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
        System.out.println("Dia útil");
        break;

    default:
        System.out.println("Opção inválida");
}
```

As duas soluções podem produzir o mesmo resultado.

---

# Uma solução não é necessariamente a única solução

É importante entender que cada desenvolvedor pode pensar de uma maneira diferente.

O fato de existirem várias formas de resolver um problema não significa necessariamente que uma delas esteja errada.

O mais importante é que a solução:

* Funcione corretamente.
* Seja fácil de entender.
* Seja adequada ao contexto.
* Seja fácil de manter.
* Não complique desnecessariamente o código.

Neste exercício, utilizamos uma característica da linguagem Java — o comportamento de continuar para os próximos `case` quando não existe `break` — para agrupar valores que possuem o mesmo comportamento.

---

# Atenção ao `fall-through`

Apesar de termos utilizado o `fall-through` propositalmente neste exercício, é importante tomar cuidado.

Por exemplo:

```java
case 1:
    System.out.println("Domingo");

case 2:
    System.out.println("Segunda-feira");
```

Nesse caso, se `dia` for `1`, serão impressos:

```text
Domingo
Segunda-feira
```

Isso acontece porque não existe `break` depois do `case 1`.

No nosso exercício, isso foi utilizado propositalmente:

```java
case 1:
case 7:
    System.out.println("Final de semana");
    break;
```

Aqui o comportamento é desejado, porque `1` e `7` devem produzir exatamente o mesmo resultado.

---

# Resumo

O exercício consiste em classificar os dias da semana:

```text
1 → Final de semana
2 → Dia útil
3 → Dia útil
4 → Dia útil
5 → Dia útil
6 → Dia útil
7 → Final de semana
```

Podemos agrupar os `case` com o mesmo resultado:

```java
switch (dia) {
    case 1:
    case 7:
        System.out.println("Final de semana");
        break;

    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
        System.out.println("Dia útil");
        break;

    default:
        System.out.println("Opção inválida");
        break;
}
```

Essa é uma das funcionalidades interessantes do `switch`: podemos utilizar vários `case` para executar o mesmo bloco de código.

---

# Conclusão

O exercício foi simples, mas serviu para praticar mais um pouco o `switch` e mostrar que existem diferentes maneiras de resolver um mesmo problema.

Também vimos na prática como podemos aproveitar o comportamento de **fall-through** para agrupar vários `case` que possuem a mesma ação.

Conforme aprendemos mais sobre Java, orientação a objetos e padrões de projeto, teremos um leque cada vez maior de ferramentas para escolher a melhor solução para cada problema.

Até a próxima aula! 🚀
