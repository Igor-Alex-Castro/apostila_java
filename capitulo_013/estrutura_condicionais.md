# Aula — Estruturas Condicionais em Java

Nesta aula, vamos continuar estudando **estruturas condicionais em Java**, com foco nos comandos:

* `if`
* `else`
* `else if`

Também veremos um conceito importante: **escopo de variáveis**.

---

## 1. Estrutura Condicional `if`

O `if` significa **"se"**.

Ele permite executar determinado bloco de código somente quando uma condição for verdadeira.

### Exemplo do dia a dia

Imagine a seguinte situação:

> Se tiver dinheiro, vou comprar comida.
> Se não tiver dinheiro, não vou comprar comida.

Em Java, podemos representar essa lógica utilizando o `if`:

```java
if (temDinheiro) {
    System.out.println("Vou comprar comida");
}
```

A condição será analisada e o bloco será executado somente se ela for `true`.

---

# 2. Estrutura `else`

O `else` significa **"senão"**.

Ele é utilizado quando queremos executar um bloco de código caso a condição do `if` seja falsa.

### Estrutura

```java
if (condicao) {
    // executado se a condição for verdadeira
} else {
    // executado se a condição for falsa
}
```

### Exemplo

```java
if (temDinheiro) {
    System.out.println("Vou comprar comida");
} else {
    System.out.println("Não vou comprar comida");
}
```

Nesse caso:

* Se `temDinheiro` for `true`, executa o primeiro bloco.
* Se `temDinheiro` for `false`, executa o `else`.

---

## 3. O `else` não possui condição

Uma característica importante do `else` é que ele **não precisa de uma condição própria**.

Por exemplo:

```java
if (autorizado) {
    System.out.println("Pode comprar bebida");
} else {
    System.out.println("Não pode comprar bebida");
}
```

O Java entende que o `else` será executado quando a condição do `if` for falsa.

Não fazemos:

```java
else (condicao) {
}
```

O correto é simplesmente:

```java
else {
}
```

---

# 4. `else` sempre está relacionado a um `if`

Não é possível utilizar um `else` sozinho.

❌ Incorreto:

```java
else {
    System.out.println("Executou");
}
```

O `else` precisa estar associado a um `if`.

✅ Correto:

```java
if (condicao) {
    System.out.println("Executou o IF");
} else {
    System.out.println("Executou o ELSE");
}
```

---

# 5. `if` e `else` formam uma estrutura condicional

Podemos pensar da seguinte forma:

```text
        condição
           |
      +----+----+
      |         |
    true      false
      |         |
     IF       ELSE
```

Ou seja:

* Condição verdadeira → `if`
* Condição falsa → `else`

---

# 6. Mais de duas condições

Nem sempre teremos apenas duas possibilidades.

Imagine que queremos classificar jogadores de futebol de acordo com a idade:

| Idade               | Categoria |
| ------------------- | --------- |
| Menor que 15        | Infantil  |
| Entre 15 e 18       | Juvenil   |
| Maior ou igual a 18 | Adulto    |

Nesse caso, precisamos analisar **mais de duas condições**.

O `if` + `else` sozinho não é suficiente.

Para isso, utilizamos o `else if`.

---

# 7. Estrutura `else if`

O `else if` significa, basicamente:

> "Senão, se..."

Ele permite verificar uma nova condição caso a condição anterior seja falsa.

### Estrutura

```java
if (condicao1) {

} else if (condicao2) {

} else {

}
```

Podemos ter vários `else if` em uma mesma estrutura.

---

# 8. Exemplo com categorias de idade

Vamos criar uma variável para representar a idade:

```java
int idade = 17;
```

Agora podemos verificar a categoria:

```java
if (idade < 15) {
    System.out.println("Categoria infantil");
} else if (idade >= 15 && idade < 18) {
    System.out.println("Categoria juvenil");
} else {
    System.out.println("Categoria adulto");
}
```

Como `idade` vale `17`, temos:

```text
17 < 15
```

Resultado:

```text
false
```

Então o Java passa para o próximo `else if`:

```text
17 >= 15 && 17 < 18
```

Resultado:

```text
true
```

Portanto, será exibido:

```text
Categoria juvenil
```

---

# 9. Podemos utilizar apenas `else` na última condição

No exemplo anterior, poderíamos pensar em criar uma terceira condição:

```java
else if (idade >= 18) {
    System.out.println("Categoria adulto");
}
```

Porém, isso não é necessariamente necessário.

Podemos simplesmente utilizar:

```java
else {
    System.out.println("Categoria adulto");
}
```

Isso acontece porque as condições anteriores já verificaram os outros casos.

Se a idade:

* não é menor que 15;
* não está entre 15 e 18;

então, automaticamente, ela pertence ao último caso.

---

# 10. Cadeia de `if`, `else if` e `else`

Podemos ter uma estrutura como:

```java
if (condicao1) {

} else if (condicao2) {

} else if (condicao3) {

} else {

}
```

O Java verifica as condições **de cima para baixo**.

Assim que encontrar uma condição verdadeira, ele executa aquele bloco e ignora os demais `else if` e o `else`.

---

## Exemplo

```java
int idade = 12;

if (idade < 15) {
    System.out.println("Categoria infantil");
} else if (idade >= 15 && idade < 18) {
    System.out.println("Categoria juvenil");
} else {
    System.out.println("Categoria adulto");
}
```

Como `idade` é `12`, a primeira condição é verdadeira:

```text
12 < 15 → true
```

Então será executado:

```text
Categoria infantil
```

As outras condições não serão analisadas.

---

# 11. Exemplo com idade 45

Se fizermos:

```java
int idade = 45;
```

Teremos:

```text
45 < 15 → false
```

Depois:

```text
45 >= 15 && 45 < 18 → false
```

Como nenhuma das condições anteriores foi verdadeira, o Java executará o `else`:

```text
Categoria adulto
```

---

# 12. Exemplo completo

```java
public class Aula05 {
    public static void main(String[] args) {

        int idade = 17;

        if (idade < 15) {
            System.out.println("Categoria infantil");
        } else if (idade >= 15 && idade < 18) {
            System.out.println("Categoria juvenil");
        } else {
            System.out.println("Categoria adulto");
        }
    }
}
```

### Resultado

Com:

```java
int idade = 17;
```

A saída será:

```text
Categoria juvenil
```

---

# 13. Trabalhando com uma variável de categoria

Também podemos armazenar o resultado em uma variável.

Por exemplo:

```java
String categoria;
```

Depois podemos definir o valor dessa variável dentro da estrutura condicional:

```java
String categoria;

if (idade < 15) {
    categoria = "Infantil";
} else if (idade >= 15 && idade < 18) {
    categoria = "Juvenil";
} else {
    categoria = "Adulto";
}

System.out.println(categoria);
```

Dessa maneira, primeiro determinamos a categoria e depois imprimimos o resultado.

---

# 14. Escopo de variáveis

Um conceito importante apresentado na aula é o **escopo**.

Escopo representa a região do código onde uma variável pode ser utilizada.

As chaves:

```java
{
    
}
```

delimitam um bloco de código.

Por exemplo:

```java
if (idade < 15) {
    String categoria = "Infantil";
}
```

A variável `categoria` foi criada dentro do bloco do `if`.

Por isso, ela possui **escopo local**.

---

# 15. Escopo local

Variáveis criadas dentro de um método ou bloco possuem escopo local.

Exemplo:

```java
public static void main(String[] args) {

    int idade = 17;

}
```

A variável `idade` pode ser utilizada dentro daquele escopo.

Da mesma forma:

```java
if (idade < 15) {

    String categoria = "Infantil";

}
```

A variável `categoria` existe dentro daquele bloco.

---

# 16. Variáveis locais precisam ser inicializadas

Uma regra importante do Java é:

> Variáveis locais precisam ser inicializadas antes de serem utilizadas.

Por exemplo:

```java
String categoria;

System.out.println(categoria);
```

Esse código gera erro de compilação porque `categoria` foi declarada, mas não recebeu um valor.

---

# 17. Problema de inicialização dentro do `if`

Observe o código:

```java
String categoria;

if (idade < 15) {
    categoria = "Infantil";
} else if (idade < 18) {
    categoria = "Juvenil";
}

System.out.println(categoria);
```

Nesse caso, o compilador pode identificar que existe uma possibilidade de `categoria` não receber nenhum valor antes de ser utilizada.

Por isso, ocorre um erro de compilação.

O Java precisa ter certeza de que a variável foi inicializada.

---

# 18. Inicializando a variável previamente

Uma alternativa é inicializar a variável antes das condições:

```java
String categoria = "";

if (idade < 15) {
    categoria = "Infantil";
} else if (idade < 18) {
    categoria = "Juvenil";
}

System.out.println(categoria);
```

Agora a variável já possui um valor inicial.

Caso nenhuma condição seja atendida, ela continuará contendo:

```text
""
```

---

# 19. Sobrescrevendo o valor

Quando fazemos:

```java
String categoria = "";
```

e posteriormente:

```java
categoria = "Infantil";
```

o valor anterior é substituído.

Ou seja:

```text
categoria = ""
```

depois:

```text
categoria = "Infantil"
```

O valor atual da variável passa a ser:

```text
Infantil
```

---

# 20. Resumo da aula

Nesta aula aprendemos:

✔ `if` — executa um bloco quando uma condição é verdadeira.

✔ `else` — executa um bloco quando o `if` é falso.

✔ `else` não possui uma condição própria.

✔ `else` precisa estar associado a um `if`.

✔ `else if` permite verificar múltiplas condições.

✔ Em uma cadeia de condições, o Java executa o primeiro bloco cuja condição seja verdadeira.

✔ Depois que uma condição é atendida, os demais `else if` e o `else` são ignorados.

✔ Podemos utilizar `else` para representar o último caso quando todas as condições anteriores forem falsas.

✔ Variáveis locais precisam ser inicializadas antes de serem utilizadas.

✔ O escopo define onde uma variável pode ser acessada.

---

# Encerramento

Agora você já conhece as principais estruturas condicionais do Java:

```java
if
else if
else
```

Essas estruturas permitem que o programa tome decisões com base em diferentes condições.

Na próxima aula, podemos continuar avançando nos **operadores lógicos e estruturas condicionais**.
