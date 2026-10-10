# Orientação a Objetos — Classes, Objetos e Variáveis de Referência

## 1. Introdução

Nesta etapa, eles iniciam o estudo de **Orientação a Objetos** em Java.

A parte introdutória do Java trabalhou principalmente com lógica de programação e sintaxe básica. A partir deste ponto, eles começam a estudar conceitos utilizados no desenvolvimento de aplicações, especialmente a forma como Java representa elementos do mundo real por meio de **classes e objetos**.

---

# 2. Variáveis Primitivas

Antes de trabalhar com objetos, eles utilizam variáveis de tipos primitivos.

Por exemplo:

```java
int idade = 12;
char sexo = 'M';
```

Cada variável armazena um valor simples.

Nesse modelo, `idade` e `sexo` são variáveis independentes. Não existe, por meio dessas variáveis isoladas, uma estrutura que indique diretamente que os dois valores pertencem à mesma pessoa.

Por exemplo:

```java
int idade = 12;
char sexo = 'M';
String nome = "Torres";
```

Os valores estão separados.

É nesse ponto que entra a Orientação a Objetos.

---

# 3. O que é Orientação a Objetos?

A Orientação a Objetos busca representar elementos do **mundo real** dentro do mundo computacional.

A ideia é agrupar informações que possuem relação entre si.

Por exemplo, uma pessoa pode possuir:

- nome;
- idade;
- sexo.

Em vez de tratar cada informação de maneira completamente independente, eles podem agrupá-las em uma estrutura que represente essa pessoa.

Esse agrupamento dará origem a um **objeto**.

---

# 4. O que é um Objeto?

Um objeto pode ser entendido como um espaço de memória que reúne diferentes dados relacionados a uma mesma entidade.

Por exemplo, um objeto do tipo `Pessoa` pode possuir:

```text
Nome: Torres
Idade: 12
Sexo: M
```

Essas informações pertencem ao mesmo objeto.

Também pode existir outro objeto do mesmo tipo:

```text
Nome: Luffy
Idade: 18
Sexo: M
```

Nesse caso, existem dois objetos diferentes em memória, mas ambos seguem a mesma estrutura.

```text
Objeto 1 — Pessoa
    nome  = Torres
    idade = 12
    sexo  = M

Objeto 2 — Pessoa
    nome  = Luffy
    idade = 18
    sexo  = M
```

---

# 5. O que é uma Classe?

Uma **classe** funciona como um modelo ou template que define a estrutura que os objetos terão.

Podemos imaginar uma classe como uma forma utilizada para produzir objetos.

Por exemplo, uma classe `Pessoa` pode definir os seguintes atributos:

```text
nome
idade
sexo
```

A partir dessa classe, podem ser criados diversos objetos `Pessoa`.

```text
Classe Pessoa
       |
       +---- Objeto Pessoa 1
       |
       +---- Objeto Pessoa 2
       |
       +---- Objeto Pessoa 3
```

A classe define a estrutura; os objetos representam as instâncias concretas dessa estrutura.

---

# 6. Classe como Representação do Mundo Real

As classes podem representar elementos do mundo real.

Alguns exemplos:

### Carro

```text
marca
modelo
anoDeFabricacao
```

### Funcionário

```text
matricula
cpf
nome
```

### Pessoa

```text
nome
idade
sexo
```

Esses dados são chamados de **atributos**, pois representam características daquilo que está sendo modelado.

---

# 7. Classes de Domínio

As classes que representam elementos ou conceitos relacionados ao negócio são frequentemente chamadas de **classes de domínio** ou **Model**.

Elas são utilizadas para representar informações importantes para o domínio da aplicação.

Por exemplo:

```text
Pessoa
Funcionário
Carro
Produto
Cliente
```

Nem toda classe de uma aplicação representa necessariamente algo do mundo real. Existem classes relacionadas a outras responsabilidades técnicas, como acesso a banco de dados, serviços e configurações.

Nesta etapa, o foco está nas classes que representam entidades do domínio.

---

# 8. Criando uma Classe

Eles podem criar uma classe `Pessoa` para representar uma pessoa.

Exemplo:

```java
public class Pessoa {

    public String nome;
    public int idade;
    public char sexo;
}
```

Essa classe possui três atributos:

```text
nome
idade
sexo
```

A classe, nesse momento, funciona como um **template**.

Ela define quais características os objetos `Pessoa` poderão possuir.

---

# 9. Atributos

Os atributos representam as características de um objeto.

Na classe:

```java
public class Pessoa {

    public String nome;
    public int idade;
    public char sexo;
}
```

Eles possuem:

| Atributo | Tipo | Representa |
|---|---|---|
| `nome` | `String` | Nome da pessoa |
| `idade` | `int` | Idade da pessoa |
| `sexo` | `char` | Sexo da pessoa |

Os atributos ficam associados ao objeto criado a partir da classe.

---

# 10. Classes e o Método `main`

Uma classe que serve como modelo para objetos não precisa necessariamente possuir um método `main`.

O método:

```java
public static void main(String[] args)
```

é utilizado como ponto de entrada para execução de uma aplicação Java.

Uma classe de domínio como `Pessoa` pode simplesmente representar a estrutura dos objetos:

```java
public class Pessoa {

    public String nome;
    public int idade;
    public char sexo;
}
```

Eles podem utilizar outra classe para executar testes e criar objetos.

---

# 11. Criando um Objeto

Para criar um objeto, eles podem utilizar a classe como tipo e a palavra-chave `new`.

Exemplo:

```java
Pessoa pessoa = new Pessoa();
```

Essa declaração possui duas partes importantes:

```java
Pessoa pessoa
```

e:

```java
new Pessoa()
```

A primeira parte declara uma **variável de referência** do tipo `Pessoa`.

A segunda parte cria um novo objeto `Pessoa`.

---

# 12. Variável de Referência

Ao trabalhar com objetos, eles passam a utilizar variáveis de referência.

Por exemplo:

```java
Pessoa pessoa;
```

Nesse caso, `pessoa` é uma variável de referência capaz de fazer referência a um objeto do tipo `Pessoa`.

Quando fazem:

```java
Pessoa pessoa = new Pessoa();
```

temos:

```text
Variável de referência
        |
        v
     objeto
     Pessoa
```

A variável de referência permite acessar o objeto ao qual ela está associada.

---

# 13. O Papel do `new`

A palavra-chave `new` é utilizada para criar um novo objeto.

Exemplo:

```java
Pessoa pessoa = new Pessoa();
```

Nesse caso:

```java
new Pessoa()
```

cria um novo objeto.

A variável:

```java
pessoa
```

passa a fazer referência a esse objeto.

---

# 14. Duas Variáveis e Dois Objetos

Eles podem criar mais de um objeto a partir da mesma classe:

```java
Pessoa pessoa1 = new Pessoa();
Pessoa pessoa2 = new Pessoa();
```

Nesse caso, existem dois objetos diferentes.

```text
pessoa1 ─────> Objeto Pessoa 1

pessoa2 ─────> Objeto Pessoa 2
```

Mesmo que ambos tenham sido criados a partir da mesma classe, cada objeto possui seu próprio espaço em memória e seus próprios valores.

---

# 15. Acessando os Atributos

Depois de criar um objeto, eles podem acessar seus atributos utilizando o operador `.`.

Exemplo:

```java
Pessoa pessoa = new Pessoa();

pessoa.nome = "Torres";
pessoa.idade = 12;
pessoa.sexo = 'M';
```

O operador `.` permite acessar os atributos disponíveis no objeto referenciado pela variável.

Podemos visualizar:

```text
pessoa
   |
   v
+------------------+
| Objeto Pessoa    |
|                  |
| nome  = Torres   |
| idade = 12       |
| sexo  = M        |
+------------------+
```

Quando utilizam:

```java
pessoa.nome
```

eles acessam o atributo `nome` daquele objeto.

Quando utilizam:

```java
pessoa.idade
```

eles acessam o atributo `idade`.

E:

```java
pessoa.sexo
```

acessa o atributo `sexo`.

---

# 16. A Variável de Referência como um "Controle Remoto"

Uma forma de visualizar a relação entre variável e objeto é imaginar a variável de referência como um **controle remoto**.

A variável não representa diretamente todos os dados do objeto. Ela permite chegar até o objeto ao qual está fazendo referência.

Por exemplo:

```java
Pessoa pessoa = new Pessoa();
```

Podemos imaginar:

```text
pessoa
  |
  | referência
  v
+--------------------+
| Objeto Pessoa      |
|                    |
| nome               |
| idade              |
| sexo               |
+--------------------+
```

A partir da referência:

```java
pessoa.nome
```

eles conseguem acessar o atributo `nome`.

---

# 17. Alterando os Atributos

Os atributos podem receber valores:

```java
pessoa.nome = "Torres";
pessoa.idade = 12;
pessoa.sexo = 'M';
```

Depois disso, os dados ficam associados ao objeto.

Podemos pensar no objeto como:

```text
Pessoa
├── nome  = Torres
├── idade = 12
└── sexo  = M
```

---

# 18. Lendo os Atributos

Para acessar os valores armazenados, eles podem utilizar novamente a variável de referência:

```java
System.out.println(pessoa.nome);
System.out.println(pessoa.idade);
System.out.println(pessoa.sexo);
```

Nesse caso, eles não estão atribuindo novos valores. Estão apenas acessando os valores existentes no objeto.

---

# 19. Imprimindo a Variável de Referência

Se eles fizerem:

```java
System.out.println(pessoa);
```

não estarão solicitando diretamente um atributo específico.

A variável `pessoa` é uma **variável de referência**.

Por isso, sua impressão não representa simplesmente o conteúdo de `nome`, `idade` ou `sexo`.

O comportamento padrão da impressão de um objeto envolve uma representação associada ao objeto, que pode aparecer como uma informação relacionada à referência/endereço lógico do objeto.

Para acessar os dados específicos, eles devem indicar o atributo:

```java
System.out.println(pessoa.nome);
```

ou:

```java
System.out.println(pessoa.idade);
```

---

# 20. Importando uma Classe de Outro Pacote

Quando uma classe está em outro pacote, eles precisam disponibilizá-la para utilização por meio de `import`, quando aplicável.

Por exemplo:

```java
import caminho.do.pacote.Pessoa;
```

Depois disso, podem utilizar:

```java
Pessoa pessoa = new Pessoa();
```

Também é possível utilizar o nome completo da classe, incluindo o pacote, embora isso deixe o código mais difícil de ler.

Por isso, normalmente o `import` é utilizado para facilitar a leitura.

---

# 21. Organização em Pacotes

Eles podem organizar as classes em diferentes pacotes.

Por exemplo:

```text
src
└── main
    └── java
        └── dominio
            └── Pessoa.java
```

E podem manter classes de teste em outro pacote:

```text
src
└── test
    └── java
        └── teste
            └── PessoaTeste.java
```

A ideia principal é separar responsabilidades e organizar melhor o projeto.

---

# 22. Classe x Objeto

É importante diferenciar os dois conceitos.

### Classe

É o modelo ou template.

Exemplo:

```java
public class Pessoa {
    public String nome;
    public int idade;
    public char sexo;
}
```

### Objeto

É uma instância criada a partir da classe.

Exemplo:

```java
Pessoa pessoa = new Pessoa();
```

Podemos resumir:

```text
Classe
   ↓
define a estrutura
   ↓
Objetos
   ↓
possuem seus próprios valores
```

---

# 23. Variável de Referência x Objeto

Também é importante não confundir a variável de referência com o objeto.

Na declaração:

```java
Pessoa pessoa = new Pessoa();
```

temos:

```text
Pessoa pessoa
     ↓
variável de referência

new Pessoa()
     ↓
objeto criado
```

A variável de referência aponta para o objeto.

Visualmente:

```text
pessoa ───────────────> objeto Pessoa
                          |
                          +── nome
                          +── idade
                          +── sexo
```

---

# 24. Resumo

Nesta etapa, eles aprenderam que:

- Variáveis primitivas armazenam valores simples.
- Dados relacionados podem ser agrupados por meio de objetos.
- A Orientação a Objetos busca representar elementos do mundo real no mundo computacional.
- Uma **classe** funciona como um modelo ou template.
- Um **objeto** é criado a partir de uma classe.
- Os dados de um objeto são representados por seus **atributos**.
- A palavra-chave `new` é utilizada para criar objetos.
- Uma variável que referencia um objeto é chamada de **variável de referência**.
- O operador `.` permite acessar os atributos do objeto.
- Uma mesma classe pode dar origem a vários objetos.
- Cada objeto possui seus próprios valores.
- Classes de domínio podem representar conceitos do domínio da aplicação.
- Uma classe de domínio não precisa possuir um método `main`.
- O `main` funciona como ponto de entrada para execução de uma aplicação.
- Classes podem ser organizadas em pacotes.
- Classes de outros pacotes podem ser utilizadas por meio de `import`.

---

# 25. Modelo Mental

Para memorizar a relação entre os conceitos:

```text
CLASSE
  │
  │ define a estrutura
  ↓
OBJETO
  │
  │ possui
  ↓
ATRIBUTOS
  │
  ├── nome
  ├── idade
  └── sexo
```

E a variável de referência funciona como o meio utilizado para acessar esse objeto:

```text
Variável de referência
          │
          │ referência
          ↓
       OBJETO
          │
          ├── nome
          ├── idade
          └── sexo
```

A principal ideia é:

> **A classe define o modelo, o objeto é uma instância desse modelo e a variável de referência permite acessar o objeto.**
