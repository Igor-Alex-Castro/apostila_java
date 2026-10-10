# Gabarito dos exercícios práticos

Abaixo estão sugestões de solução e pontos importantes para cada exercício. O objetivo é revisar lógica, não apenas copiar código.

## 1) Cálculo de média

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Digite a 1ª nota:");
        double nota1 = sc.nextDouble();

        System.out.println("Digite a 2ª nota:");
        double nota2 = sc.nextDouble();

        System.out.println("Digite a 3ª nota:");
        double nota3 = sc.nextDouble();

        double media = (nota1 + nota2 + nota3) / 3;

        if (media >= 7) {
            System.out.println("Aprovado");
        } else {
            System.out.println("Reprovado");
        }

        System.out.println("Média: " + media);
    }
}
```

## 2) Verificação de maioridade

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite a idade:");
        int idade = sc.nextInt();

        if (idade < 18) {
            System.out.println("Menor de idade");
        } else if (idade < 60) {
            System.out.println("Maior de idade");
        } else {
            System.out.println("Idoso");
        }
    }
}
```

## 3) Conversão de temperatura

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Escolha a conversão:\n1 - Celsius para Fahrenheit\n2 - Fahrenheit para Celsius");
        int opcao = sc.nextInt();

        System.out.println("Digite o valor:");
        double valor = sc.nextDouble();

        if (opcao == 1) {
            double fahrenheit = (valor * 9 / 5) + 32;
            System.out.println("Resultado: " + fahrenheit + "°F");
        } else if (opcao == 2) {
            double celsius = (valor - 32) * 5 / 9;
            System.out.println("Resultado: " + celsius + "°C");
        } else {
            System.out.println("Opção inválida");
        }
    }
}
```

## 4) Calculadora simples

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Digite o primeiro número:");
        double n1 = sc.nextDouble();

        System.out.println("Digite o segundo número:");
        double n2 = sc.nextDouble();

        System.out.println("Escolha a operação (+, -, *, /):");
        String operacao = sc.next();

        switch (operacao) {
            case "+":
                System.out.println(n1 + n2);
                break;
            case "-":
                System.out.println(n1 - n2);
                break;
            case "*":
                System.out.println(n1 * n2);
                break;
            case "/":
                if (n2 == 0) {
                    System.out.println("Erro: divisão por zero");
                } else {
                    System.out.println(n1 / n2);
                }
                break;
            default:
                System.out.println("Operação inválida");
        }
    }
}
```

## 5) Número par ou ímpar

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite um número:");
        int numero = sc.nextInt();

        if (numero % 2 == 0) {
            System.out.println("Par");
        } else {
            System.out.println("Ímpar");
        }

        if (numero > 0) {
            System.out.println("Positivo");
        } else if (numero < 0) {
            System.out.println("Negativo");
        } else {
            System.out.println("Zero");
        }
    }
}
```

## 6) Tabuada

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite um número:");
        int numero = sc.nextInt();

        for (int i = 1; i <= 10; i++) {
            System.out.println(numero + " x " + i + " = " + (numero * i));
        }
    }
}
```

## 7) Soma dos números de 1 a 100

```java
public class Main {
    public static void main(String[] args) {
        int soma = 0;

        for (int i = 1; i <= 100; i++) {
            soma += i;
        }

        System.out.println("Soma: " + soma);
    }
}
```

## 8) Números positivos e negativos

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int positivos = 0;
        int negativos = 0;
        int zeros = 0;

        for (int i = 1; i <= 10; i++) {
            System.out.println("Digite o número " + i + ":");
            int numero = sc.nextInt();

            if (numero > 0) {
                positivos++;
            } else if (numero < 0) {
                negativos++;
            } else {
                zeros++;
            }
        }

        System.out.println("Positivos: " + positivos);
        System.out.println("Negativos: " + negativos);
        System.out.println("Zeros: " + zeros);
    }
}
```

## 9) Maior e menor valor

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int maior = Integer.MIN_VALUE;
        int menor = Integer.MAX_VALUE;
        int soma = 0;

        for (int i = 1; i <= 5; i++) {
            System.out.println("Digite o número " + i + ":");
            int numero = sc.nextInt();

            soma += numero;

            if (numero > maior) {
                maior = numero;
            }

            if (numero < menor) {
                menor = numero;
            }
        }

        double media = soma / 5.0;

        System.out.println("Maior: " + maior);
        System.out.println("Menor: " + menor);
        System.out.println("Média: " + media);
    }
}
```

## 10) Verificação de senha

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String usuarioCorreto = "admin";
        String senhaCorreta = "1234";

        System.out.println("Digite o usuário:");
        String usuario = sc.next();

        System.out.println("Digite a senha:");
        String senha = sc.next();

        if (usuario.equals(usuarioCorreto) && senha.equals(senhaCorreta)) {
            System.out.println("Login realizado com sucesso");
        } else {
            System.out.println("Usuário ou senha inválidos");
        }
    }
}
```

## 11) Menu de opções

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int opcao;

        do {
            System.out.println("Menu:");
            System.out.println("1 - Cadastrar");
            System.out.println("2 - Listar");
            System.out.println("3 - Sair");
            opcao = sc.nextInt();

            switch (opcao) {
                case 1:
                    System.out.println("Cadastro realizado");
                    break;
                case 2:
                    System.out.println("Listando dados");
                    break;
                case 3:
                    System.out.println("Saindo...");
                    break;
                default:
                    System.out.println("Opção inválida");
            }
        } while (opcao != 3);
    }
}
```

## 12) Pesquisa em vetor

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        int[] numeros = {10, 25, 8, 42, 77, 3, 15, 61, 9, 20};
        Scanner sc = new Scanner(System.in);

        System.out.println("Digite o número a pesquisar:");
        int busca = sc.nextInt();

        boolean encontrado = false;

        for (int i = 0; i < numeros.length; i++) {
            if (numeros[i] == busca) {
                System.out.println("Número encontrado na posição: " + i);
                encontrado = true;
                break;
            }
        }

        if (!encontrado) {
            System.out.println("Número não encontrado");
        }
    }
}
```

## 13) Média de notas em vetor

```java
public class Main {
    public static void main(String[] args) {
        double[] notas = {8.5, 7.0, 9.2, 6.5, 10.0};
        double soma = 0;
        double maior = notas[0];
        double menor = notas[0];

        for (int i = 0; i < notas.length; i++) {
            soma += notas[i];

            if (notas[i] > maior) {
                maior = notas[i];
            }

            if (notas[i] < menor) {
                menor = notas[i];
            }
        }

        double media = soma / notas.length;

        System.out.println("Média: " + media);
        System.out.println("Maior: " + maior);
        System.out.println("Menor: " + menor);
    }
}
```

## 14) Matriz de notas

```java
public class Main {
    public static void main(String[] args) {
        double[][] notas = {
            {8.0, 7.5, 9.0, 6.5},
            {7.0, 8.0, 8.5, 9.0},
            {6.0, 7.0, 8.0, 7.5}
        };

        double maior = Double.MIN_VALUE;
        double menor = Double.MAX_VALUE;

        for (int i = 0; i < notas.length; i++) {
            double somaAluno = 0;
            for (int j = 0; j < notas[i].length; j++) {
                somaAluno += notas[i][j];

                if (notas[i][j] > maior) {
                    maior = notas[i][j];
                }

                if (notas[i][j] < menor) {
                    menor = notas[i][j];
                }
            }

            double mediaAluno = somaAluno / notas[i].length;
            System.out.println("Média do aluno " + (i + 1) + ": " + mediaAluno);
        }

        System.out.println("Maior nota: " + maior);
        System.out.println("Menor nota: " + menor);
    }
}
```

## 15) Soma das diagonais de uma matriz

```java
public class Main {
    public static void main(String[] args) {
        int[][] matriz = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        int somaPrincipal = 0;
        int somaSecundaria = 0;

        for (int i = 0; i < matriz.length; i++) {
            somaPrincipal += matriz[i][i];
            somaSecundaria += matriz[i][matriz.length - 1 - i];
        }

        System.out.println("Diagonal principal: " + somaPrincipal);
        System.out.println("Diagonal secundária: " + somaSecundaria);
    }
}
```

## 16) Inversão de números

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite um número:");
        int numero = sc.nextInt();

        int invertido = 0;

        while (numero != 0) {
            invertido = invertido * 10 + (numero % 10);
            numero /= 10;
        }

        System.out.println("Número invertido: " + invertido);
    }
}
```

## 17) Contagem de vogais e consoantes

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite uma palavra:");
        String palavra = sc.next().toLowerCase();

        int vogais = 0;
        int consoantes = 0;

        for (int i = 0; i < palavra.length(); i++) {
            char letra = palavra.charAt(i);

            if (letra >= 'a' && letra <= 'z') {
                if (letra == 'a' || letra == 'e' || letra == 'i' || letra == 'o' || letra == 'u') {
                    vogais++;
                } else {
                    consoantes++;
                }
            }
        }

        System.out.println("Vogais: " + vogais);
        System.out.println("Consoantes: " + consoantes);
    }
}
```

## 18) Verificação de número primo

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite um número:");
        int numero = sc.nextInt();

        boolean primo = true;

        if (numero <= 1) {
            primo = false;
        } else {
            for (int i = 2; i <= numero / 2; i++) {
                if (numero % i == 0) {
                    primo = false;
                    break;
                }
            }
        }

        if (primo) {
            System.out.println("É primo");
        } else {
            System.out.println("Não é primo");
        }
    }
}
```

## 19) Soma de números pares

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Digite o início:");
        int inicio = sc.nextInt();

        System.out.println("Digite o fim:");
        int fim = sc.nextInt();

        int soma = 0;

        for (int i = inicio; i <= fim; i++) {
            if (i % 2 == 0) {
                soma += i;
            }
        }

        System.out.println("Soma dos pares: " + soma);
    }
}
```

## 20) Sistema de cobrança simples

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Digite o preço do produto:");
        double preco = sc.nextDouble();

        System.out.println("Digite a quantidade:");
        int quantidade = sc.nextInt();

        System.out.println("Digite o percentual de desconto:");
        double desconto = sc.nextDouble();

        double subtotal = preco * quantidade;
        double valorDesconto = subtotal * (desconto / 100);
        double total = subtotal - valorDesconto;

        System.out.println("Subtotal: " + subtotal);
        System.out.println("Desconto: " + valorDesconto);
        System.out.println("Total: " + total);
    }
}
```

## 21) Lista de nomes

```java
public class Main {
    public static void main(String[] args) {
        String[] nomes = {"Ana", "Bruno", "Carlos", "Diana"};

        for (String nome : nomes) {
            System.out.println(nome);
        }

        System.out.println("Quantidade: " + nomes.length);
        System.out.println("Primeiro: " + nomes[0]);
        System.out.println("Último: " + nomes[nomes.length - 1]);
    }
}
```

## 22) Jogo de adivinhação

```java
import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        Scanner sc = new Scanner(System.in);

        int numeroSorteado = random.nextInt(10) + 1;

        for (int tentativa = 1; tentativa <= 3; tentativa++) {
            System.out.println("Tentativa " + tentativa + ". Digite um número de 1 a 10:");
            int chute = sc.nextInt();

            if (chute == numeroSorteado) {
                System.out.println("Você acertou!");
                return;
            } else if (chute < numeroSorteado) {
                System.out.println("Chute menor do que o número");
            } else {
                System.out.println("Chute maior do que o número");
            }
        }

        System.out.println("Você perdeu. Número sorteado: " + numeroSorteado);
    }
}
```

## 23) Validando entrada de usuário

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Digite a idade:");
        int idade = sc.nextInt();

        if (idade < 0 || idade > 120) {
            System.out.println("Idade inválida");
        } else {
            System.out.println("Idade válida");
        }
    }
}
```

## 24) Cálculo de fatorial

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Digite um número:");
        int numero = sc.nextInt();

        int fatorial = 1;

        for (int i = 2; i <= numero; i++) {
            fatorial *= i;
        }

        System.out.println("Fatorial: " + fatorial);
    }
}
```

## 25) Exercício de revisão final

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[] numeros = new int[5];
        int soma = 0;
        int maior = Integer.MIN_VALUE;
        int menor = Integer.MAX_VALUE;

        for (int i = 0; i < 5; i++) {
            System.out.println("Digite o número " + (i + 1) + ":");
            numeros[i] = sc.nextInt();
            soma += numeros[i];

            if (numeros[i] > maior) {
                maior = numeros[i];
            }

            if (numeros[i] < menor) {
                menor = numeros[i];
            }
        }

        double media = soma / 5.0;
        int acimaDaMedia = 0;
        int abaixoDaMedia = 0;

        for (int numero : numeros) {
            if (numero > media) {
                acimaDaMedia++;
            } else if (numero < media) {
                abaixoDaMedia++;
            }
        }

        System.out.println("Média: " + media);
        System.out.println("Acima da média: " + acimaDaMedia);
        System.out.println("Abaixo da média: " + abaixoDaMedia);
        System.out.println("Maior: " + maior);
        System.out.println("Menor: " + menor);
    }
}
```

## Dica de estudo

O gabarito deve ser usado como validação, não como atalho. Tente resolver primeiro e, depois, compare sua lógica com a solução proposta.
