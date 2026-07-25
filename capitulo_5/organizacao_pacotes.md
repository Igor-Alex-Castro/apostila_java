# Criando e Organizando Pacotes no Java

## Nomeando o Projeto

Ao criar um projeto Java, **não é aconselhável utilizar traços (`-`) no nome**. Embora possa funcionar em alguns casos, não é uma prática recomendada.

Um padrão comum é utilizar:

```text
com.seusite.projeto
```

Por exemplo:

```text
academy.devdojo.maratonajava.introducao
```

Esse padrão segue a convenção de utilizar o **domínio invertido** da empresa ou site.

---

# Renomeando um Pacote

Caso queira alterar o nome de um pacote:

1. Clique com o botão direito sobre o pacote.
2. Selecione **Refactor**.
3. Escolha **Rename** (atalho: `Shift + F6`).
4. Digite o novo nome.

A IDE atualizará automaticamente todas as referências.

---

# Estrutura de Pacotes

Dentro da pasta `src`, podemos criar uma hierarquia de pacotes:

```text
src
└── academy
    └── devdojo
        └── maratonajava
            └── introducao
```

Todas as classes devem ser criadas dentro de algum pacote.

Por exemplo:

```text
academy.devdojo.maratonajava.introducao
```

---

# Movendo Classes para um Pacote

Se você já possui uma classe criada fora do pacote, basta:

1. Arrastá-la para o pacote desejado.
2. Confirmar a operação na IDE.

Após isso, uma linha será adicionada automaticamente ao início do arquivo:

```java
package academy.devdojo.maratonajava.introducao;
```

---

# Declaração do Pacote

Toda classe que pertence a um pacote deve começar com a declaração:

```java
package academy.devdojo.maratonajava.introducao;
```

Essa deve ser a **primeira linha de código do arquivo** (desconsiderando comentários).

## Exemplo

```java
package academy.devdojo.maratonajava.introducao;

public class OlaDevDojo {

    public static void main(String[] args) {
        System.out.println("Olá DevDojo!");
    }

}
```

---

# Por Que Utilizamos Pacotes?

Pacotes servem para **organizar o código**.

Em projetos pequenos isso pode não parecer importante, mas em sistemas grandes podemos ter centenas ou milhares de classes.

O nome completo de uma classe é composto por:

```text
nome_do_pacote + nome_da_classe
```

Exemplo:

```text
academy.devdojo.maratonajava.introducao.OlaDevDojo
```

Isso evita conflitos entre classes com o mesmo nome em diferentes partes do sistema.

---

# Compilando o Projeto

Para compilar:

```text
Ctrl + F9
```

Após a compilação, a IDE gera os arquivos `.class` dentro da pasta de saída (geralmente `out`).

### Estrutura gerada

```text
out
└── production
    └── projeto
        └── academy
            └── devdojo
                └── maratonajava
                    └── introducao
                        └── OlaDevDojo.class
```

Observe que a estrutura de diretórios segue exatamente a estrutura dos pacotes.

---

# Executando o Projeto

Para executar a classe que contém o método `main`:

```text
Shift + F10
```

Ou clique com o botão direito sobre a classe e escolha:

```text
Run 'NomeDaClasse'
```

---

# Resumo

- Utilize nomes de pacotes seguindo o padrão de domínio invertido.
- Todas as classes devem pertencer a um pacote.
- A declaração `package` deve ser a primeira linha de código do arquivo.
- Pacotes ajudam na organização e evitam conflitos entre classes.
- `Ctrl + F9` compila o projeto.
- `Shift + F10` executa o programa.
- A estrutura de pastas gerada na compilação segue a estrutura dos pacotes.
````
