# Gabarito dos exercícios teóricos

Este documento serve como apoio para revisão. Use-o após tentar responder por conta própria.

## Fundamentos

### 1) O que é Java e qual é a diferença entre compilação e execução?
Java é uma linguagem de programação orientada a objetos, compilada e executada em uma máquina virtual. A compilação transforma o código-fonte em bytecode, e a execução acontece na JVM (Java Virtual Machine), que interpreta ou compila o bytecode para a arquitetura do sistema.

### 2) Qual é a função da JVM?
A JVM é responsável por executar o bytecode Java. Ela gerencia memória, interpreta/compila instruções e torna o código Java independente de plataforma.

### 3) O que é uma variável e para que serve?
Uma variável é um espaço de memória nomeado usado para armazenar valores durante a execução do programa. Ela serve para guardar dados que serão usados, comparados ou manipulados.

### 4) Explique a diferença entre tipo primitivo e tipo referenciado.
Tipos primitivos armazenam valores simples diretamente na memória (ex.: int, double, boolean). Tipos referenciados armazenam referências para objetos, como strings, arrays e classes criadas pelo desenvolvedor.

### 5) Quais são os tipos primitivos mais usados em Java?
int, double, float, boolean, char, long, short, byte.

### 6) Qual a diferença entre `int`, `double` e `boolean`?
- int: inteiro, sem casas decimais
- double: número decimal com maior precisão
- boolean: valor lógico, verdadeiro ou falso

### 7) O que acontece se você tentar atribuir um valor incompatível a uma variável?
O programa normalmente gera erro de compilação, porque o Java exige compatibilidade de tipos.

## Operadores

### 8) Qual a diferença entre operadores aritméticos e operadores relacionais?
Aritméticos realizam cálculos matemáticos (+, -, *, /, %). Relacionais comparam valores para verificar relações (==, !=, <, >, <=, >=).

### 9) Explique o uso de `&&`, `||` e `!`.
- &&: E lógico
- ||: OU lógico
- !: negação lógica

### 10) O que é operador ternário e em que situação ele é útil?
É uma forma curta de escrever uma condição if/else. Exemplo: `resultado = nota >= 7 ? "Aprovado" : "Reprovado";`

### 11) Quando usar `==` e quando usar `=`?
- `=`: atribuição
- `==`: comparação

### 12) Como funcionam os operadores de incremento e decremento (`++`, `--`)?
Eles aumentam ou diminuem o valor de uma variável em 1. Ex.: `x++` é equivalente a `x = x + 1`.

## Condicionais

### 13) Qual a diferença entre `if`, `else if` e `else`?
- if: testa uma condição
- else if: testa outra condição caso a anterior seja falsa
- else: executa quando todas as anteriores forem falsas

### 14) Quando usar `switch` em vez de vários `if` encadeados?
Quando há várias opções fixas com base em um único valor, como dia da semana, menu de opções ou status.

### 15) O que são estruturas condicionais e qual a importância delas no desenvolvimento de software?
Estruturas condicionais permitem que o programa tome decisões com base em condições. Isso é essencial para controlar fluxo e comportamentos.

### 16) Qual é a vantagem de usar `switch` em casos com muitas opções fixas?
Deixa o código mais legível e organizado, além de facilitar manutenção quando há muitas opções possíveisa.

## Laços de repetição

### 17) Qual a diferença entre `for`, `while` e `do while`?
- for: usado quando se sabe a quantidade de repetições
- while: repete enquanto a condição for verdadeira
- do while: executa ao menos uma vez antes de testar a condição

### 18) Quando um `for` é mais útil do que um `while`?
Quando a quantidade de iterações é conhecida ou facilmente controlada por contador.

### 19) O que acontece se a condição de um `while` nunca for falsa?
Gera um loop infinito, travando a execução do programa.

### 20) Qual a diferença entre `break` e `continue`?
- break: encerra o laço imediatamente
- continue: pula a iteração atual e continua com a próxima

### 21) Por que loops infinitos são perigosos?
Porque causam travamento, consumo excessivo de CPU e podem congelar a aplicação.

## Arrays

### 22) O que é um array?
É uma estrutura que armazena vários valores do mesmo tipo em uma única variável.

### 23) Qual a diferença entre array unidimensional e multidimensional?
Unidimensional é uma lista simples; multidimensional é uma tabela, como matriz com linhas e colunas.

### 24) Como acessar um elemento de um vetor?
Pelo índice. Ex.: `vetor[0]` acessa o primeiro elemento.

### 25) O que acontece se você tentar acessar uma posição inválida de um array?
O Java lança `ArrayIndexOutOfBoundsException`.

### 26) Qual a diferença entre `for` clássico e `for-each`?
- for clássico: permite controlar índice e manipular posições
- for-each: mais simples para percorrer todos os elementos sem acessar índices

### 27) Quando um array multidimensional é útil?
Quando o problema precisa de dados em tabela, como matrizes de notas, jogos ou grades.

## Lógica e boas práticas

### 28) Por que é importante validar dados antes de processá-los?
Para evitar erros, entradas inválidas e comportamentos inesperados no sistema.

### 29) O que torna um código fácil de entender e manter?
Nome de variáveis claros, organização, comentários mínimos, lógica simples e consistência.

### 30) Como você faria para testar um programa antes de considerá-lo pronto?
Executar casos válidos, casos inválidos, casos limites e verificar se a saída está correta.

### 31) O que é um algoritmo?
É uma sequência lógica de passos para resolver um problema.

### 32) Como você explica a diferença entre lógica de programação e linguagem de programação?
Lógica de programação é o raciocínio para resolver problemas. Linguagem de programação é a ferramenta usada para escrever esse raciocínio.

## Questões comportamentais / de raciocínio

### 33) Como você resolveria um problema que parece simples, mas tem muitos casos de borda?
Analisaria entradas válidas e inválidas, testaria limites e quebraria o problema em etapas simples.

### 34) Como você reagiria se seu código estivesse errado e o erro só aparecesse em produção?
Reveria a lógica, testaria cenários reais, usaria logs e validaria com casos de uso e dados reais.

### 35) Explique como você organiza seu raciocínio para desenvolver uma solução em Java.
Entendo o problema, identifico entrada/saída, escrevo os passos, implemento em pequenos blocos e testo casos comuns e limites.

### 36) O que você considera um código legível para um time de desenvolvimento?
Clareza, nomes bons, estrutura consistente, pouca duplicação e fácil manutenção.

## Dica final

O objetivo da teoria não é decorar, e sim compreender a lógica por trás das estruturas e saber explicar o raciocínio quando necessário.
