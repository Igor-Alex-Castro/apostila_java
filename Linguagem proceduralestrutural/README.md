# Linguagem procedural / estruturada

A linguagem procedural, também conhecida como linguagem estruturada, é aquela em que o código é organizado em sequência lógica, usando estruturas como:

- sequência
- decisão (`if`, `else`, `switch`)
- repetição (`for`, `while`, `do while`)
- funções ou procedimentos

Esse paradigma prioriza a execução passo a passo do programa, sem depender de conceitos como classes, objetos ou herança.

## Características principais

- O programa é escrito como uma série de instruções executadas em ordem.
- O foco está na lógica de processamento e na resolução do problema.
- Funções ajudam a organizar o código em blocos reutilizáveis.
- Não há a ideia central de "entidade com estado e comportamento" como na POO.

## Exemplo conceitual

Em uma abordagem procedural, o código normalmente fica assim:

```java
public class Main {
    public static void main(String[] args) {
        int idade = 18;

        if (idade >= 18) {
            System.out.println("Maior de idade");
        } else {
            System.out.println("Menor de idade");
        }
    }
}
```

Nesse exemplo, o foco está na lógica condicional e no fluxo do programa, e não em objetos.

## Diferência da POO

A POO organiza o software em objetos que representam algo do mundo real ou do problema. Já a linguagem procedural/estruturada organiza o programa em algoritmos e funções.

Na prática:

- Procedural/estruturada: resolve o problema com instruções e funções.
- POO: resolve o problema com objetos, classes e interações entre eles.

## Relação com Java

Java é uma linguagem orientada a objetos, mas antes de aprender POO, é importante entender os fundamentos da lógica de programação, estruturas condicionais, laços, operadores e arrays. Essa base é o que torna a escrita de programas Java mais clara e correta mais tarde.

## Conteúdo desta pasta

Aqui você encontra os fundamentos do Java estudados em uma abordagem procedural/estruturada, como:

- operadores
- condicionais
- laços de repetição
- arrays
- conceitos básicos de lógica e sintaxe

## Exercícios de revisão

Para praticar conceitos teóricos e exercícios de entrevista, acesse:

- [Exercícios de Java procedural / estruturado](./exercicios/README.md)
- [Gabarito dos exercícios teóricos](./exercicios/gabarito-exercicios-teoricos.md)
- [Gabarito dos exercícios práticos](./exercicios/gabarito-exercicios-praticos.md)

Acesse os arquivos desta pasta para seguir a sequência de estudo.

### Último item de revisão

- [Exercícios de revisão final](./exercicios/README.md)
