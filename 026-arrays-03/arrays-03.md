# Arrays em Java — Parte 03

## Introdução

Nesta aula continuamos estudando **arrays em Java**.

Agora vamos aprender como:

* Percorrer todos os elementos de um array.
* Utilizar o índice para acessar cada posição.
* Evitar erros relacionados aos índices.
* Descobrir o tamanho de um array usando `length`.
* Entender que o tamanho de um array não pode ser alterado dinamicamente.
* Entender o que acontece quando uma variável passa a referenciar outro array.
* Compreender, de forma introdutória, o funcionamento do **Garbage Collector**.

---

# Percorrendo um array

Considere o seguinte array:

```java
String[] nomes = new String[3];
```

Podemos armazenar valores utilizando seus índices:

```java
nomes[0] = "Maria";
nomes[1] = "João";
nomes[2] = "Pedro";
```

O array ficará assim:

```text
+---------+---------+---------+
| "Maria" |  "João" | "Pedro" |
+---------+---------+---------+
     0         1         2
```

Como temos três posições, os índices disponíveis são:

```text
0
1
2
```

O índice `3` já não existe.

---

# Utilizando o `for`

Uma maneira simples de percorrer todos os elementos de um array é utilizando o `for`.

Exemplo:

```java
String[] nomes = new String[3];

nomes[0] = "Maria";
nomes[1] = "João";
nomes[2] = "Pedro";

for (int i = 0; i < 3; i++) {
    System.out.println(nomes[i]);
}
```

Resultado:

```text
Maria
João
Pedro
```

---

# Entendendo o índice

O `for` começa com:

```java
int i = 0;
```

Isso acontece porque o primeiro índice do array é `0`.

Depois temos:

```java
i < 3
```

Enquanto `i` for menor que `3`, o loop continuará executando.

A sequência será:

```text
i = 0 → nomes[0]
i = 1 → nomes[1]
i = 2 → nomes[2]
```

Quando:

```text
i = 3
```

a condição:

```java
i < 3
```

será falsa e o loop será encerrado.

---

# O problema de utilizar um número fixo

Imagine que posteriormente alteramos o array:

```java
String[] nomes = new String[4];

nomes[0] = "Maria";
nomes[1] = "João";
nomes[2] = "Pedro";
nomes[3] = "Ana";
```

Se mantivermos:

```java
for (int i = 0; i < 3; i++) {
    System.out.println(nomes[i]);
}
```

apenas três posições serão percorridas.

Resultado:

```text
Maria
João
Pedro
```

O `"Ana"` não será impresso.

Portanto, utilizar o número `3` diretamente no `for` não é uma boa prática quando o tamanho do array pode mudar.

---

# O problema de ultrapassar o tamanho do array

Também podemos cometer o erro contrário.

Imagine:

```java
String[] nomes = new String[3];
```

Temos os índices:

```text
0
1
2
```

Se fizermos:

```java
for (int i = 0; i < 4; i++) {
    System.out.println(nomes[i]);
}
```

o programa tentará acessar:

```text
nomes[0]
nomes[1]
nomes[2]
nomes[3]
```

Porém, `nomes[3]` não existe.

Isso causará uma exceção:

```text
ArrayIndexOutOfBoundsException
```

Essa exceção acontece quando tentamos acessar uma posição que está fora dos limites do array.

---

# Utilizando `length`

Para evitar esses problemas, podemos utilizar a propriedade `length` do array.

Exemplo:

```java
String[] nomes = new String[3];

nomes[0] = "Maria";
nomes[1] = "João";
nomes[2] = "Pedro";

for (int i = 0; i < nomes.length; i++) {
    System.out.println(nomes[i]);
}
```

O `length` retorna o tamanho do array.

Nesse caso:

```java
nomes.length
```

retorna:

```text
3
```

---

# Por que utilizar `length`?

O principal benefício é que o código se adapta automaticamente ao tamanho do array.

Se tivermos:

```java
String[] nomes = new String[3];
```

então:

```java
nomes.length
```

será:

```text
3
```

Se mudarmos para:

```java
String[] nomes = new String[4];
```

então:

```java
nomes.length
```

passará a retornar:

```text
4
```

Portanto, podemos manter o mesmo `for`:

```java
for (int i = 0; i < nomes.length; i++) {
    System.out.println(nomes[i]);
}
```

Não precisamos alterar a condição manualmente.

---

# `length` representa o tamanho, não o último índice

Essa é uma informação muito importante.

Se temos:

```java
String[] nomes = new String[4];
```

então:

```java
nomes.length
```

é igual a:

```text
4
```

Porém, os índices são:

```text
0
1
2
3
```

Portanto:

```text
length = 4
último índice = 3
```

Por isso utilizamos:

```java
i < nomes.length
```

e não:

```java
i <= nomes.length
```

### Forma correta

```java
for (int i = 0; i < nomes.length; i++) {
    System.out.println(nomes[i]);
}
```

### Forma incorreta

```java
for (int i = 0; i <= nomes.length; i++) {
    System.out.println(nomes[i]);
}
```

Na forma incorreta, quando `i` chegar ao valor `4`, tentaremos acessar:

```java
nomes[4]
```

Mas o último índice é `3`.

Isso causará:

```text
ArrayIndexOutOfBoundsException
```

---

# Arrays possuem tamanho fixo

Outra característica importante dos arrays é que seu tamanho é **fixo**.

Quando fazemos:

```java
String[] nomes = new String[3];
```

criamos um array com exatamente três posições.

Não podemos simplesmente aumentar o tamanho desse mesmo array durante a execução.

Por exemplo, não existe uma operação como:

```java
nomes.aumentarTamanho(5);
```

O tamanho original permanece `3`.

---

# Criando um novo array

Se precisarmos de um array maior, podemos criar outro array.

Por exemplo:

```java
nomes = new String[5];
```

Agora a variável `nomes` passará a referenciar um novo array com cinco posições.

Podemos representar a situação inicialmente assim:

```text
nomes
  |
  v
+-------+-------+-------+
|       |       |       |
+-------+-------+-------+
   0       1       2
```

Depois:

```java
nomes = new String[5];
```

A variável passa a apontar para outro objeto:

```text
nomes
  |
  v
+-------+-------+-------+-------+-------+
| null  | null  | null  | null  | null  |
+-------+-------+-------+-------+-------+
   0       1       2       3       4
```

---

# O que acontece com o array antigo?

Essa é uma parte importante para entender como referências funcionam em Java.

Imagine:

```java
String[] nomes = new String[3];
```

Temos:

```text
nomes
  |
  v
+-----+-----+-----+
|     |     |     |
+-----+-----+-----+
```

Depois fazemos:

```java
nomes = new String[5];
```

Agora temos:

```text
             +-----+-----+-----+
             |     |     |     |
             +-----+-----+-----+
              antigo array
                   ↑
                   |
               sem referência


nomes
  |
  v
+-----+-----+-----+-----+-----+
|     |     |     |     |     |
+-----+-----+-----+-----+-----+
            novo array
```

A variável `nomes` deixou de apontar para o primeiro objeto e passou a apontar para o segundo.

---

# O que acontece com o objeto antigo?

Se não existir nenhuma outra referência apontando para o antigo array, ele ficará **inacessível pelo programa**.

Esse objeto poderá posteriormente ser removido da memória pelo **Garbage Collector**.

De forma simplificada:

```text
Array antigo
     |
     X
sem referência
     |
     v
Garbage Collector
     |
     v
memória liberada
```

O Garbage Collector é responsável por identificar objetos que não podem mais ser utilizados pelo programa e liberar a memória ocupada por eles.

---

# Referência para objetos

É importante entender que:

```java
String[] nomes = new String[3];
```

não significa que `nomes` seja o próprio objeto array.

A variável `nomes` contém uma **referência** para o objeto.

Podemos imaginar:

```text
nomes
  |
  | referência
  v
+-----+-----+-----+
|     |     |     |
+-----+-----+-----+
```

Quando fazemos:

```java
nomes = new String[5];
```

a referência muda:

```text
nomes
  |
  | referência
  v
+-----+-----+-----+-----+-----+
|     |     |     |     |     |
+-----+-----+-----+-----+-----+
```

O objeto anterior continua existindo por algum tempo, mas não pode mais ser acessado através da variável `nomes`.

---

# Por que desenhar a memória?

Quando estamos começando a estudar Java, pode ser difícil visualizar o que acontece com objetos e referências.

Uma boa técnica é desenhar no papel.

Por exemplo:

```java
String[] nomes = new String[3];
```

Podemos desenhar:

```text
nomes ────────────> [ ][ ][ ]
```

Depois:

```java
nomes = new String[5];
```

Podemos desenhar:

```text
                 [ ][ ][ ]
                  antigo
                    ↑
                    X
                 sem referência


nomes ────────────> [ ][ ][ ][ ][ ]
                      novo
```

Essa representação ajuda a entender que a variável não é o objeto em si. Ela possui uma referência para ele.

---

# Exemplo completo

```java
public class Aula34 {

    public static void main(String[] args) {

        String[] nomes = new String[3];

        nomes[0] = "Maria";
        nomes[1] = "João";
        nomes[2] = "Pedro";

        for (int i = 0; i < nomes.length; i++) {
            System.out.println(nomes[i]);
        }
    }
}
```

Saída:

```text
Maria
João
Pedro
```

---

# Resumo

Nesta aula aprendemos:

* Podemos percorrer um array utilizando `for`.
* Os índices dos arrays começam em `0`.
* O último índice é sempre `length - 1`.
* `length` retorna o tamanho do array.
* É recomendado utilizar `length` para percorrer arrays.
* O tamanho de um array é fixo.
* Não podemos aumentar ou diminuir diretamente o tamanho de um array existente.
* Para ter um array com outro tamanho, precisamos criar um novo array.
* Uma variável pode deixar de referenciar um objeto e passar a referenciar outro.
* Um objeto que não possui mais nenhuma referência pode ser coletado pelo **Garbage Collector**.
* Arrays são objetos e as variáveis armazenam referências para esses objetos.

## Regra importante

Para percorrer um array, utilize:

```java
for (int i = 0; i < nomes.length; i++) {
    System.out.println(nomes[i]);
}
```

Em vez de:

```java
for (int i = 0; i < 3; i++) {
    System.out.println(nomes[i]);
}
```

Dessa forma, o código funciona independentemente de o array possuir 3, 4, 10 ou 100 posições.

---

## Próxima aula

Na próxima aula, continuaremos estudando arrays e veremos outras formas de trabalhar com seus elementos.
