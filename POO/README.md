# Programação Orientada a Objetos (POO)

A Programação Orientada a Objetos (POO) é um paradigma de programação que organiza o código em objetos e classes. Em vez de escrever um programa apenas como instruções sequenciais, a ideia é modelar partes do sistema como entidades que possuem:

- atributos (características)
- métodos (ações/comportamentos)
- estado interno
- relações entre si

## Conceito principal

Na POO, a unidade base é o objeto. Um objeto pode representar, por exemplo:

- um carro
- um cliente
- uma conta bancária
- um aluno

Cada objeto tem dados e comportamentos relacionados a ele.

## Exemplo conceitual

```java
class Carro {
    String modelo;
    int ano;

    void ligar() {
        System.out.println("Carro ligado");
    }
}

public class Main {
    public static void main(String[] args) {
        Carro meuCarro = new Carro();
        meuCarro.modelo = "Civic";
        meuCarro.ano = 2024;
        meuCarro.ligar();
    }
}
```

Nesse exemplo, o objeto `meuCarro` é uma instância da classe `Carro`, e o código organiza o problema em termos de entidade e comportamento.

## Principais pilares da POO

### 1. Encapsulamento

Os dados e comportamentos ficam agrupados dentro de uma classe, e o acesso pode ser controlado para proteger o estado do objeto.

### 2. Herança

Uma classe pode herdar características de outra, reutilizando código e organizando melhor o sistema.

### 3. Polimorfismo

Objetos diferentes podem responder da mesma forma a uma mesma mensagem, de maneiras distintas.

### 4. Abstração

Você foca apenas nos detalhes importantes do objeto, ignorando detalhes irrelevantes do funcionamento interno.

## Diferença da linguagem procedural

Na programação procedural, o foco principal é o fluxo do algoritmo. Já na POO, o foco está na modelagem do problema por meio de objetos e classes.

## Relação com Java

Java é uma linguagem fortemente orientada a objetos. Isso significa que, para escrever programas em Java de forma eficiente e organizada, é importante entender bem os conceitos de classes, objetos, encapsulamento, herança e métodos.

## Conteúdo desta pasta

Nesta pasta, você encontra os conteúdos relacionados à orientação a objetos, começando pelos conceitos básicos e avançando para a estrutura da programação em Java com classes e objetos.
