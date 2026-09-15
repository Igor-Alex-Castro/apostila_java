# Java: Como Funciona

## 1. O problema inicial

Existem vários sistemas operacionais, como:

- Windows
- Linux
- macOS

Cada sistema operacional entende programas de forma diferente.

Por isso, antigamente, um programa desenvolvido para **Windows** normalmente não funcionava no **Linux** ou no **macOS**.

---

## 2. A ideia do Java

O Java surgiu com o conceito:

> **Write Once, Run Anywhere**

> **"Escreva uma vez, rode em qualquer lugar."**

A solução foi criar uma camada intermediária entre:

- o sistema operacional;
- a aplicação.

Essa camada é chamada de **JVM (Java Virtual Machine)**.

---

## 3. Como funciona a JVM

Em vez da aplicação conversar diretamente com o sistema operacional:

```text
Aplicação → Sistema Operacional
```

O Java faz assim:

```text
Aplicação Java → JVM → Sistema Operacional
```

Ou seja:

- o programa Java conversa com a **JVM**;
- a JVM conversa com:
  - Windows;
  - Linux;
  - macOS.

Assim, o mesmo programa pode ser executado em qualquer sistema operacional.

---

## 4. Fluxo completo do Java

### Etapa 1 — Código-fonte

Você escreve um arquivo:

```text
MeuPrograma.java
```

Esse arquivo é chamado de:

- código-fonte;
- source code.

### Etapa 2 — Compilação

O Java é uma linguagem compilada.

O compilador do Java chama-se:

```text
javac
```

Ele transforma:

```text
.java → .class
```

Exemplo:

```text
MeuPrograma.java
        ↓
MeuPrograma.class
```

---

## 5. O que é o Bytecode

O arquivo `.class` contém o:

**Bytecode**

O bytecode **não** é entendido diretamente pelo sistema operacional.

Quem entende o bytecode é a **JVM**.

---

## 6. Execução

Depois da compilação:

```text
.class → JVM → Sistema Operacional
```

A JVM interpreta e executa o bytecode.

Por isso o Java é considerado uma linguagem:

- compilada;
- interpretada.

---

## 7. Estrutura visual do processo

```text
Código Java (.java)
        ↓
Compilador (javac)
        ↓
Bytecode (.class)
        ↓
JVM
        ↓
Windows / Linux / macOS
```

---

## 8. Vantagem principal

Você escreve o código apenas uma vez:

```text
MeuPrograma.java
```

E consegue executá-lo em vários sistemas operacionais diferentes.

---

# 9. JDK e JRE

## JDK (Java Development Kit)

Usado para:

- desenvolver aplicações Java.

Contém:

- JVM;
- compilador (`javac`);
- ferramentas de debug;
- bibliotecas.

Quem utiliza:

- desenvolvedores.

---

## JRE (Java Runtime Environment)

Usado apenas para:

- executar aplicações Java.

Contém:

- JVM.

Quem utiliza:

- usuários finais.

---

## 10. Diferença entre JDK e JRE

| JDK | JRE |
|------|-----|
| Desenvolver e executar | Apenas executar |
| Possui compilador (`javac`) | Não possui compilador |
| Utilizado por programadores | Utilizado por usuários |

---

## 11. Retrocompatibilidade do Java

Uma das maiores vantagens do Java é a **retrocompatibilidade**.

### Exemplo

Um sistema criado no **Java 8** normalmente consegue ser executado em versões mais recentes da plataforma.

Isso facilita:

- manutenção;
- atualização;
- evolução do sistema.

Na maioria dos casos, sem a necessidade de alterar significativamente o código-fonte.

---

# 12. Resumo final

O funcionamento do Java pode ser resumido da seguinte forma:

1. Você escreve um arquivo `.java`;
2. O compilador (`javac`) transforma esse arquivo em `.class`;
3. O arquivo `.class` contém o **bytecode**;
4. A **JVM** executa o bytecode;
5. A JVM se comunica com o sistema operacional.

Fluxo completo:

```text
.java
   ↓
javac
   ↓
.class (Bytecode)
   ↓
JVM
   ↓
Sistema Operacional
```

---

# Frase principal para lembrar

> **O Java não roda diretamente no sistema operacional.**
>
> **Ele roda na JVM, e a JVM roda sobre o sistema operacional.**
