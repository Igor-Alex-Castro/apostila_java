# Tipos Primitivos e Declaração de Variáveis em Java

## Introdução

Em Java, os dados podem ser armazenados em variáveis.

Antes de armazenar qualquer valor, precisamos informar ao Java qual será o tipo de dado que aquela variável irá guardar.

Exemplo:

```java
int idade = 10;
```

Nesse caso:

- `int` → tipo da variável.
- `idade` → nome da variável.
- `10` → valor armazenado.

---

# Criando Classes para Estudo

Durante o curso, foi utilizada uma convenção para organizar as aulas:

```text
Aula01OlaDevDojo
Aula02TiposPrimitivos
Aula03Operadores
```

> ⚠️ **Importante:** Em projetos reais, não é comum nomear classes dessa forma.
>
> Isso foi feito apenas para facilitar o acompanhamento das aulas em ordem cronológica.

---

# Atalho para Criar o Método `main`

Ao invés de digitar:

```java
public static void main(String[] args) {

}
```

O IntelliJ oferece o atalho:

```text
psvm + Tab
```

Resultado:

```java
public static void main(String[] args) {

}
```

Esse é um dos atalhos mais utilizados por desenvolvedores Java.

---

# Executando Classes

## Executar a classe atual

Atalho:

```text
Ctrl + Shift + F10
```

Executa a classe em que você está trabalhando.

---

## Executar a última configuração

Atalho:

```text
Shift + F10
```

Executa a última classe que foi executada.

> ⚠️ **Atenção:**
>
> Muitos iniciantes alteram uma classe e esquecem que estão executando outra.
>
> Sempre confira qual classe está selecionada antes de executar.

---

# O que são Tipos Primitivos?

Tipos primitivos são os tipos mais básicos do Java.

Eles armazenam valores simples diretamente na memória.

O Java possui **8 tipos primitivos**.

| Tipo | Valor armazenado |
|---|---|
| `byte` | Números inteiros pequenos |
| `short` | Números inteiros curtos |
| `int` | Números inteiros |
| `long` | Números inteiros grandes |
| `float` | Números decimais |
| `double` | Números decimais com maior precisão |
| `char` | Um único caractere |
| `boolean` | Verdadeiro ou falso |

---

# Os 8 Tipos Primitivos

## `byte`

Utilizado para números inteiros pequenos.

```java
byte idade = 10;
```

### Faixa

```text
-128 até 127
```

---

## `short`

Utilizado para números inteiros curtos.

```java
short numero = 1000;
```

### Faixa

```text
-32.768 até 32.767
```

---

## `int`

É o tipo mais utilizado para números inteiros.

```java
int idade = 30;
```

### Faixa

```text
-2.147.483.648 até 2.147.483.647
```

---

## `long`

Utilizado para números inteiros muito grandes.

```java
long populacaoMundial = 8000000000L;
```

Observe o `L` no final do valor.

---

## `float`

Utilizado para números decimais.

```java
float salario = 2500.50F;
```

Observe o `F` no final do valor.

---

## `double`

É o tipo decimal mais utilizado.

```java
double preco = 19.99;
```

---

## `char`

Armazena um único caractere.

```java
char sexo = 'M';
```

Utiliza **aspas simples**.

---

## `boolean`

Armazena valores de verdadeiro ou falso.

```java
boolean ativo = true;
```

Valores possíveis:

```text
true
false
```

---

# Todos os Tipos Primitivos São Minúsculos

Os tipos primitivos são palavras reservadas do Java.

### ✅ Correto

```java
int idade;
double salario;
boolean ativo;
```

### ❌ Errado

```java
Int idade;
Double salario;
Boolean ativo;
```

Embora existam classes chamadas `Integer`, `Double` e `Boolean`, elas não são tipos primitivos.

São **classes wrapper**, assunto que será estudado mais adiante.

---

# Declarando Variáveis

A sintaxe básica é:

```text
tipo nomeDaVariavel;
```

Exemplo:

```java
int idade;
```

Nesse momento, a variável foi declarada, mas ainda não recebeu um valor.

---

# Inicializando Variáveis

Inicializar significa atribuir um valor à variável.

```java
int idade = 10;
```

Agora o valor `10` está armazenado na variável.

---

# Convenção de Nomes para Variáveis

Em Java, utilizamos **camelCase** para nomes de variáveis.

## Uma palavra

```java
int idade;
String nome;
double salario;
```

## Múltiplas palavras

```java
int idadeDoPai;
double salarioMensal;
String nomeCompleto;
```

### Regra

- A primeira palavra começa com letra minúscula.
- As demais palavras começam com letra maiúscula.

---

# Convenção para Classes

Classes utilizam **PascalCase**.

Exemplos:

```text
Pessoa
Cliente
ContaCorrente
CalculadoraImposto
```

Cada palavra começa com letra maiúscula.

---

# Variáveis em Inglês

Uma boa prática é utilizar nomes em inglês.

### Em vez de:

```java
int idade;
String nome;
```

### Prefira:

```java
int age;
String name;
```

### Motivos

- Padrão internacional.
- Facilita trabalhar com equipes estrangeiras.
- Facilita a leitura de documentação.
- Facilita entrevistas e projetos open source.

Em projetos pessoais e durante o aprendizado, utilizar português não é um problema.

---

# Imprimindo Valores

## Valor literal

Quando colocamos um texto entre aspas, estamos imprimindo o texto literal.

```java
System.out.println("idade");
```

Saída:

```text
idade
```

---

## Valor da variável

```java
int idade = 10;

System.out.println(idade);
```

Saída:

```text
10
```

Sem aspas, o Java busca o valor armazenado na variável.

---

# Como a Variável Funciona na Memória?

Quando fazemos:

```java
int idade = 10;
```

Podemos imaginar:

```text
Variável: idade
          ↓
       +------+
       |  10  |
       +------+
```

A variável é um nome que referencia um espaço na memória.

Quando usamos:

```java
System.out.println(idade);
```

O Java busca o valor armazenado naquele espaço e imprime o resultado.

---

# Concatenação de Strings

Podemos juntar textos e variáveis utilizando o operador `+`.

Exemplo:

```java
int idade = 10;

System.out.println("A idade é " + idade);
```

Saída:

```text
A idade é 10
```

Também podemos concatenar várias partes:

```java
int idade = 10;

System.out.println("A idade é " + idade + " anos");
```

Saída:

```text
A idade é 10 anos
```

---

# Exemplo Completo

```java
public class Aula02TiposPrimitivos {

    public static void main(String[] args) {

        int idade = 10;

        System.out.println("A idade é " + idade + " anos");

    }

}
```

Saída:

```text
A idade é 10 anos
```

---

# Resumo

- Java possui **8 tipos primitivos**.
- Todos os tipos primitivos são escritos em letras minúsculas.
- Uma variável é um espaço nomeado na memória.
- Declarar uma variável não é o mesmo que inicializá-la.
- Variáveis utilizam **camelCase**.
- Classes utilizam **PascalCase**.
- Sem aspas → valor da variável.
- Com aspas → texto literal.
- O operador `+` é utilizado para concatenar textos e valores.
- Utilize nomes claros e, preferencialmente, em inglês em projetos profissionais.
