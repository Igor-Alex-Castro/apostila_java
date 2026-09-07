# Estrutura do java

## 1. Padronização do Java

O Java é mantido pela:

> **JCP (Java Community Process)**

A JCP é responsável por definir:

- padrões;
- convenções;
- evolução da linguagem;
- instalação;
- compatibilidade.

Isso garante que o Java funcione de maneira semelhante em qualquer lugar do mundo.

---

## 2. Variáveis de Ambiente

Após instalar o Java, é necessário configurar as **variáveis de ambiente**.

Elas permitem:

- acessar o Java de qualquer lugar do sistema;
- outras aplicações encontrarem o Java instalado.

### Exemplos de aplicações que utilizam essas variáveis

- IntelliJ IDEA
- Eclipse
- Maven
- Gradle
- Tomcat

---

# 3. O que é o `JAVA_HOME`

A principal variável de ambiente do Java é:

```text
JAVA_HOME
```

Ela aponta para a pasta onde o **JDK** está instalado.

### Exemplo

```text
C:\Program Files\Java\jdk-15.0.2
```

> **Importante:** o `JAVA_HOME` deve apontar para a pasta do JDK, e **não** para a pasta `bin`.

---

## 4. Pasta `bin`

Dentro do JDK existe a pasta:

```text
bin
```

Ela contém executáveis importantes, como:

- `java.exe`
- `javac.exe`

Esses arquivos são responsáveis por:

- executar programas Java;
- compilar arquivos `.java`.

---

# 5. O que é o `PATH`

O Windows possui uma variável de ambiente chamada:

```text
PATH
```

Ela armazena uma lista de diretórios que podem ser acessados globalmente.

Quando você executa o comando:

```bash
java
```

o Windows procura esse executável dentro dos diretórios configurados no **PATH**.

---

# 6. Configurando o `JAVA_HOME`

Crie uma nova variável de ambiente:

| Nome | Valor |
|------|-------|
| `JAVA_HOME` | `C:\Program Files\Java\jdk-15.0.2` |

---

# 7. Configurando o `PATH`

Adicione o seguinte valor ao **PATH**:

```text
%JAVA_HOME%\bin
```

Assim, o Windows conseguirá localizar automaticamente:

- `java.exe`;
- `javac.exe`.

---

# 8. Como `%JAVA_HOME%` funciona

A expressão:

```text
%JAVA_HOME%
```

é substituída automaticamente pelo valor armazenado na variável.

### Exemplo

```text
%JAVA_HOME%\bin
```

torna-se:

```text
C:\Program Files\Java\jdk-15.0.2\bin
```

---

# 9. Erro comum

## ❌ Configuração incorreta

### JAVA_HOME

```text
C:\Program Files\Java\jdk-15.0.2\bin
```

### PATH

```text
%JAVA_HOME%\bin
```

### Resultado

```text
...\bin\bin
```

Isso faz com que o Windows não encontre corretamente os executáveis do Java.

---

# 10. Forma correta

## ✅ Configuração correta

### JAVA_HOME

```text
C:\Program Files\Java\jdk-15.0.2
```

### PATH

```text
%JAVA_HOME%\bin
```

---

# 11. Testando o Java

Abra o terminal e execute:

```bash
java -version
```

Se tudo estiver configurado corretamente, o resultado será semelhante a:

```text
java version "15"
```

---

# 12. Testando o compilador

Execute:

```bash
javac
```

Se forem exibidas as opções do compilador, significa que:

- o Java foi instalado corretamente;
- o compilador está acessível pelo terminal.

---

# 13. Comando `where java`

Você pode descobrir todas as instalações do Java disponíveis utilizando:

```bash
where java
```

### Exemplo

```text
C:\Program Files (x86)\Common Files\Oracle\Java\java8path\java.exe
C:\Program Files (x86)\Common Files\Oracle\Java\javapath\java.exe
C:\Program Files\Java\jdk-15.0.2\bin\java.exe
```

---

# 14. Como o `where java` funciona

O Windows percorre o **PATH** de cima para baixo.

O **primeiro caminho encontrado** será utilizado para executar o comando `java`.

No exemplo anterior, o diretório:

```text
java8path
```

estava sendo utilizado antes da instalação do Java 15.

---

# 15. Problema comum da Oracle

A Oracle costuma criar automaticamente diretórios como:

- `javapath`;
- `java8path`.

Esses diretórios são adicionados automaticamente ao **PATH** e podem:

- sobrescrever versões mais recentes;
- fazer o Windows utilizar uma versão antiga do Java.

---

# 16. Como resolver

Abra:

```text
Variáveis de Ambiente → Path
```

Remova entradas semelhantes a:

```text
C:\Program Files (x86)\Common Files\Oracle\Java\java8path
```

e:

```text
C:\Program Files (x86)\Common Files\Oracle\Java\javapath
```

---

# 17. Depois de alterar o PATH

Após modificar o **PATH**, feche todos os programas que utilizam o terminal, como:

- CMD;
- PowerShell;
- VS Code;
- IntelliJ IDEA.

Depois, abra-os novamente para que as alterações sejam aplicadas.

---

# 18. Teste final

Execute novamente:

```bash
java -version
```

Agora deverá aparecer algo semelhante a:

```text
java version "15.0.2"
```

---

# 19. Resumo final

## Configuração correta

### JAVA_HOME

```text
C:\Program Files\Java\jdk-15.0.2
```

### PATH

```text
%JAVA_HOME%\bin
```

---

## Fluxo completo da configuração

```text
Instalar o JDK
        ↓
Criar a variável JAVA_HOME
        ↓
Adicionar %JAVA_HOME%\bin ao PATH
        ↓
Remover entradas antigas (javapath/java8path)
        ↓
Fechar os terminais e IDEs
        ↓
Abrir novamente
        ↓
Executar: java -version
```

---

# Principais pontos

- O **JAVA_HOME** deve apontar para a pasta do JDK.
- O **PATH** deve conter `%JAVA_HOME%\bin`.
- O comando `java -version` verifica se o Java está configurado corretamente.
- O comando `javac` confirma que o compilador está disponível.
- O comando `where java` mostra todas as instalações do Java encontradas pelo Windows.
- O Windows utiliza sempre o **primeiro caminho** encontrado no **PATH**.
- Remover entradas antigas evita conflitos entre diferentes versões do Java.
