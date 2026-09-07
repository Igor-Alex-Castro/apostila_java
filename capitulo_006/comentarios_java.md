# Comentários em Java

## O que são comentários?

Comentários são trechos de texto inseridos no código-fonte que **não afetam a execução do programa**.

Eles servem apenas para **documentar**, **explicar** ou **registrar informações** para outros desenvolvedores (ou para você mesmo no futuro).

Quando o código é compilado, os comentários são **ignorados pelo compilador** e **não aparecem no bytecode (`.class`)**.

---

# 1. Comentário de uma linha

Utiliza duas barras (`//`).

Tudo que estiver à direita das barras será considerado comentário.

```java
// Este é um comentário de uma linha

System.out.println("Olá Mundo"); // Imprime uma mensagem
```

---

# 2. Comentário de múltiplas linhas

Utiliza `/* */`.

É útil quando precisamos escrever textos maiores.

```java
/*
Este é um comentário
de múltiplas linhas.
*/
```

Também pode ser escrito em apenas uma linha:

```java
/* Comentário de múltiplas linhas */
```

---

# 3. JavaDoc

O **JavaDoc** é um tipo especial de comentário utilizado para documentar **classes**, **métodos** e **atributos**.

Sua sintaxe é:

```java
/**
 * Este é um comentário JavaDoc.
 */
```

Ao pressionar **Enter** após `/**`, a IDE geralmente gera automaticamente a estrutura do comentário.

## Exemplo

```java
/**
 * Classe responsável por calcular impostos.
 */
public class CalculadoraImposto {

}
```

---

# Tags mais utilizadas do JavaDoc

## `@param`

Descreve um parâmetro do método.

```java
/**
 * Soma dois números.
 *
 * @param a primeiro número
 * @param b segundo número
 * @return resultado da soma
 */
public int soma(int a, int b) {
    return a + b;
}
```

---

## `@return`

Descreve o valor retornado pelo método.

```java
/**
 * Retorna o nome do usuário.
 *
 * @return nome do usuário
 */
public String getNome() {
    return nome;
}
```

---

## `@throws`

Descreve as exceções lançadas pelo método.

```java
/**
 * Divide dois números.
 *
 * @throws ArithmeticException quando o divisor for zero
 */
public int dividir(int a, int b) {
    return a / b;
}
```

---

## `@see`

Cria referências para outras classes ou métodos.

```java
/**
 * @see Calculadora
 */
```

---

# JavaDoc pode conter HTML

O JavaDoc suporta algumas tags HTML.

Exemplo:

```java
/**
 * Calcula o imposto.<br>
 * Método utilizado pelo módulo financeiro.
 */
```

Ao gerar a documentação, essas tags são renderizadas corretamente.

---

# Como visualizar a documentação?

## Navegar para a implementação

No IntelliJ:

```text
Ctrl + B
```

ou

```text
Ctrl + Clique
```

Abre diretamente a implementação da classe ou método.

---

## Ver o JavaDoc

No IntelliJ:

```text
Ctrl + Q
```

Mostra o JavaDoc da classe ou método selecionado.

Isso é extremamente útil quando utilizamos bibliotecas de terceiros.

---

# Devo comentar meu código?

**Regra geral: não.**

Segundo o livro **Clean Code**, comentários frequentemente indicam que o código **não está suficientemente claro**.

### ❌ Comentário desnecessário

```java
// Imprime uma mensagem
System.out.println("Olá");
```

O próprio código já deixa isso evidente.

---

# Prefira nomes claros

### ❌ Ruim

```java
int x = 18;
```

### ✅ Melhor

```java
int idadeMinimaParaCadastro = 18;
```

Um nome bem escolhido elimina a necessidade de comentários.

---

# Quando comentários são úteis?

Existem situações em que comentários agregam valor.

## Regras de negócio incomuns

```java
// Aceita datas negativas devido à integração
// com o sistema legado XYZ.
```

---

## Workarounds

```java
// Necessário devido a um bug conhecido da API externa.
```

---

## Decisões arquiteturais

```java
// Optamos por cache local para reduzir
// chamadas ao serviço de terceiros.
```

Nesses casos, o comentário explica **o motivo da decisão**, e não apenas **o que o código faz**.

---

# O perigo dos comentários

Comentários podem ficar desatualizados.

Imagine:

```java
// Soma dois números
public int multiplicar(int a, int b) {
    return a * b;
}
```

O código foi alterado, mas o comentário não.

Quem ler poderá entender algo completamente errado.

Por isso, muitos times preferem:

- Código autoexplicativo.
- Métodos pequenos.
- Nomes claros.
- Poucos comentários.

---

# Boas práticas

## ✅ Faça

- Use **JavaDoc** em APIs públicas.
- Comente regras de negócio complexas.
- Explique decisões que não são óbvias.
- Prefira nomes descritivos.

## ❌ Evite

- Explicar o óbvio.
- Escrever comentários redundantes.
- Manter comentários desatualizados.
- Usar comentários para compensar código confuso.

---

# Resumo

Existem três tipos principais de comentários em Java.

| Tipo | Sintaxe | Uso |
|------|----------|-----|
| Uma linha | `//` | Observações rápidas |
| Múltiplas linhas | `/* */` | Textos maiores |
| JavaDoc | `/** */` | Documentação oficial da API |

---

## Principal recomendação

Escreva um código **tão claro** que ele quase não precise de comentários.

Quando for necessário comentar, explique **o porquê** de algo existir, e **não apenas o que o código faz**.
