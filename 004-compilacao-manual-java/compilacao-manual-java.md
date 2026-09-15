# Compilação Manual em Java

## Introdução

No Java, trabalhamos inicialmente com um arquivo `.java`, que é o código-fonte escrito pelo desenvolvedor.

Exemplo:

```text
OlaDevDojo.java
```

Esse arquivo passa por um processo chamado **compilação**, realizado pelo compilador Java (`javac`), gerando um arquivo `.class`.

```text
OlaDevDojo.class
```

O arquivo `.class` contém o **bytecode**, que é interpretado pela **JVM (Java Virtual Machine)**.

---

# Criando a Primeira Classe Java

## Estrutura Básica

```java
public class OlaDevDojo {

    public static void main(String[] args) {

        System.out.println("BAAAAAM");

    }
}
```

---

# Convenções de Nomenclatura

## Classes

Os nomes das classes devem seguir o padrão **PascalCase**.

### ✅ Correto

```text
OlaDevDojo
MinhaPrimeiraClasse
SistemaFinanceiro
```

### ❌ Evite

```text
oladevdojo
minhaPrimeiraClasse
```

Embora funcione tecnicamente, não segue as convenções da linguagem.

---

# Entendendo a Estrutura

## Classe

```java
public class OlaDevDojo {
}
```

- `public` → modificador de acesso.
- `class` → define uma classe.
- `OlaDevDojo` → nome da classe.

---

## Método Main

```java
public static void main(String[] args) {
}
```

É o ponto de entrada da aplicação.

---

## Exibindo Mensagens

```java
System.out.println("BAAAAAM");
```

### Regras importantes

- Textos devem ficar entre aspas duplas (`"`).
- Toda instrução termina com ponto e vírgula (`;`).

---

# Salvando o Arquivo

O nome do arquivo deve ser **exatamente igual** ao nome da classe pública.

Classe:

```java
public class OlaDevDojo {
}
```

Arquivo:

```text
OlaDevDojo.java
```

> **⚠️ Atenção:** Maiúsculas e minúsculas fazem diferença.

---

# Compilando Manualmente

Abra o **Prompt de Comando (CMD)** na pasta onde está o arquivo.

## Verificando o Java

```bash
javac
```

Se aparecer a ajuda do compilador, o Java está configurado corretamente.

---

## Gerando o Bytecode

```bash
javac OlaDevDojo.java
```

Após executar, será criado:

```text
OlaDevDojo.class
```

---

# Executando o Programa

Para executar:

```bash
java OlaDevDojo
```

Observe:

### ❌ Errado

```bash
java OlaDevDojo.class
```

### ✅ Correto

```bash
java OlaDevDojo
```

O Java encontra automaticamente o arquivo `.class`.

---

# Entendendo o Fluxo Completo

```text
OlaDevDojo.java
        │
        ▼
      javac
        │
        ▼
OlaDevDojo.class
        │
        ▼
       java
        │
        ▼
       JVM
        │
        ▼
    Resultado
```

---

# Alterou o Código? Compile Novamente!

Se você modificar:

```java
System.out.println("Novo texto");
```

É necessário gerar novamente o bytecode:

```bash
javac OlaDevDojo.java
```

Só depois execute:

```bash
java OlaDevDojo
```

Caso contrário, a JVM continuará executando a versão antiga.

---

# Como Descobrir Qual Java Está Sendo Utilizado

Às vezes existem várias instalações do Java na máquina.

No CMD execute:

```bash
where java
```

Exemplo de saída:

```text
C:\Program Files (x86)\Common Files\Oracle\Java\javapath\java.exe
C:\Program Files\Java\jdk-21\bin\java.exe
```

O Windows utiliza o **primeiro caminho encontrado** na variável `PATH`.

---

# Problema Comum: Java Apontando Para o Lugar Errado

Você encontrou algo como:

```text
C:\Program Files (x86)\Common Files\Oracle\Java\javapath\java.exe
```

ou

```text
C:\Program Files (x86)\Common Files\Oracle\Java\java8path\java.exe
```

Esses atalhos podem fazer o sistema utilizar uma versão incorreta do Java.

## Como corrigir

1. Abra **Variáveis de Ambiente**.
2. Localize a variável **Path**.
3. Remova as entradas relacionadas a:

```text
C:\Program Files (x86)\Common Files\Oracle\Java\javapath
```

ou

```text
C:\Program Files (x86)\Common Files\Oracle\Java\java8path
```

4. Mantenha apenas o caminho da JDK desejada, por exemplo:

```text
C:\Program Files\Java\jdk-21\bin
```

5. Abra um novo CMD e execute:

```bash
java -version
```

e

```bash
where java
```

para confirmar que a versão correta está sendo utilizada.

---

# Erros Comuns

## 1. Nome da Classe Diferente do Arquivo

Classe:

```java
public class oladevdojo {
}
```

Arquivo:

```text
OlaDevDojo.java
```

Erro:

```text
class oladevdojo is public, should be declared in a file named oladevdojo.java
```

### Solução

O nome da classe e do arquivo devem ser **exatamente iguais**.

---

## 2. Esquecer o Ponto e Vírgula

Código:

```java
System.out.println("Olá Mundo")
```

Erro:

```text
';' expected
```

Correção:

```java
System.out.println("Olá Mundo");
```

---

# Resumo

- Criar o arquivo `.java`.
- Escrever a classe.
- Salvar com o mesmo nome da classe.
- Compilar com:

```bash
javac NomeDaClasse.java
```

- Executar com:

```bash
java NomeDaClasse
```

- Sempre recompilar após alterações.
- Se houver problemas de versão, verificar:

```bash
where java
```

e conferir as entradas da variável `PATH`.
