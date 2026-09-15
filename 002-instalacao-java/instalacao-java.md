# Instalação do Java

## 1. Revisando como o Java funciona

O Java trabalha com um **arquivo-fonte**:

```text
.java
```

Esse é o arquivo que nós, humanos, conseguimos entender.

### Exemplo

```java
public class Pessoa {
    String nome;
}
```

Esse código é escrito em uma **linguagem de alto nível**, ou seja, uma linguagem mais fácil de ler, escrever e entender.

---

## 2. Linguagens de alto nível x baixo nível

### Alto nível

Mais próximo dos humanos.

**Exemplos:**

- Java
- Python
- Kotlin

**Características:**

- mais fácil de entender;
- desenvolvimento mais rápido;
- maior nível de abstração.

---

### Baixo nível

Mais próximo da máquina e do sistema operacional.

**Exemplo:**

- Assembly

**Características:**

- mais complexo;
- maior desempenho;
- maior performance.

---

## 3. Processo do Java

O Java transforma o código-fonte em **bytecode**.

Fluxo do processo:

```text
Arquivo (.java)
        ↓
Compilador (javac)
        ↓
Arquivo (.class)
        ↓
JVM
        ↓
Sistema Operacional
```

---

## 4. O que é o arquivo `.class`

O arquivo:

```text
.class
```

contém o **bytecode**.

Esse bytecode é entendido pela:

- **JVM (Java Virtual Machine)**

---

## 5. Função da JVM

A JVM funciona como um intermediário entre o programa Java e o sistema operacional.

Ela é responsável por:

- interpretar o bytecode;
- conversar com o sistema operacional.

A JVM possui versões específicas para:

- Windows;
- Linux;
- macOS.

Por isso, o mesmo programa Java pode ser executado em diferentes sistemas operacionais.

---

# 6. Evolução das versões do Java

Antes do Java 9, as novas versões demoravam vários anos para serem lançadas.

| Versão | Ano |
|---------|-----|
| Java 6 | 2006 |
| Java 7 | 2011 |
| Java 8 | 2014 |

---

## 7. Mudança a partir do Java 9

A Oracle percebeu que o Java estava evoluindo lentamente.

Por isso, adotou um novo modelo de lançamentos:

> **Uma nova versão a cada seis meses.**

### Objetivos

- entregar novas funcionalidades mais rapidamente;
- competir com linguagens modernas;
- receber feedback da comunidade com mais frequência.

---

## 8. Java moderno

Atualmente, o Java continua sendo uma das linguagens mais utilizadas no mercado.

Compete diretamente com linguagens como:

- Kotlin;
- C#;
- Python.

É amplamente utilizado em:

- bancos;
- sistemas corporativos;
- APIs;
- back-end;
- grandes empresas.

---

# 9. Versões LTS

## O que significa LTS?

**LTS** significa:

> **Long Term Support** (Suporte de Longo Prazo)

São versões que recebem suporte e atualizações por vários anos.

### Versões mais utilizadas pelas empresas

| Versão | Tipo |
|---------|------|
| Java 8 | LTS |
| Java 11 | LTS |
| Java 17 | LTS |
| Java 21 | LTS |

### Por que as empresas utilizam versões LTS?

Porque elas:

- são mais estáveis;
- possuem suporte prolongado;
- recebem atualizações de segurança.

---

## 10. Versões intermediárias

Exemplos:

- Java 12
- Java 13
- Java 14
- Java 15
- Java 16

Essas versões são utilizadas principalmente para:

- testar novas funcionalidades;
- experimentar recursos;
- validar novidades antes de entrarem em uma versão LTS.

---

# 11. O que é o JDK

**JDK (Java Development Kit)** é o kit de desenvolvimento do Java.

Ele contém:

- JVM;
- compilador (`javac`);
- ferramentas de debug;
- bibliotecas;
- ferramentas para desenvolvimento.

---

## 12. Download do Java

Você pode baixar o Java através de diferentes distribuições, como:

- Oracle JDK;
- OpenJDK;
- Amazon Corretto;
- Eclipse Temurin.

---

## 13. Escolhendo a versão correta

Antes do download, escolha a versão adequada para:

### Sistema operacional

- Windows;
- Linux;
- macOS.

### Arquitetura

- x64;
- ARM.

---

# 14. Instalação no Windows

## Passo 1 — Baixar o instalador

Escolha a opção:

```text
Windows x64 Installer
```

---

## Passo 2 — Executar o instalador

Siga as etapas:

```text
Next → Next → Install
```

---

## Passo 3 — Finalizar

Após concluir a instalação:

```text
Close
```

---

# 15. Onde o Java é instalado

Normalmente, o JDK é instalado em:

```text
C:\Program Files\Java
```

Exemplo:

```text
jdk-15
```

---

# 16. Estrutura da pasta do JDK

Dentro da pasta do JDK existem diversas subpastas.

A mais importante é:

```text
bin
```

Ela contém arquivos como:

- `java.exe`
- `javac.exe`

Esses executáveis permitem:

- executar programas Java;
- compilar programas Java.

---

# 17. Resumo final

## Processo completo

```text
Código Java (.java)
        ↓
Compilador (javac)
        ↓
Bytecode (.class)
        ↓
JVM
        ↓
Sistema Operacional
```

---

## Principais pontos

- Java é uma linguagem de alto nível;
- a JVM executa o bytecode;
- o JDK é utilizado para desenvolvimento;
- empresas preferem utilizar versões LTS;
- Java continua muito forte no mercado;
- cada sistema operacional possui sua própria implementação da JVM.
