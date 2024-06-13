# **Projeto DesafioControleFluxo - Documentação**
## Visão Geral
Este projeto em Java tem como objetivo verificar a validade de dois parâmetros inteiros recebidos via terminal e realizar uma contagem baseada nesses valores. Se o primeiro parâmetro for maior que o segundo, o sistema lançará uma exceção customizada denominada ParametrosInvalidosException.

## Estrutura do Projeto
O projeto consiste em duas classes principais:

1. **ParametrosInvalidosException.java:** Define a exceção customizada.
2. **Contador.java:** Contém a lógica principal do programa, incluindo a leitura de entrada do usuário e a execução da contagem.

## Classe ParametrosInvalidosException
```
/**
 * Exceção customizada que será lançada quando o segundo parâmetro
 * não for maior que o primeiro.
 */
public class ParametrosInvalidosException extends Exception {
    
    /**
     * Construtor da exceção que recebe uma mensagem de erro.
     *
     * @param mensagem A mensagem de erro a ser exibida quando a exceção for lançada.
     */
    public ParametrosInvalidosException(String mensagem) {
        super(mensagem);
    }
}

```

## Classe Contador

```
import java.util.Scanner;

/**
 * A classe Contador contém a lógica principal do programa.
 * Solicita dois parâmetros inteiros do usuário e realiza uma contagem
 * baseada nesses valores, verificando a validade dos parâmetros.
 */
public class Contador {
    
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();
        
        try {
            // Chamando o método contendo a lógica de contagem
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException e) {
            // Imprimir a mensagem: O segundo parâmetro deve ser maior que o primeiro
            System.out.println(e.getMessage());
        } finally {
            // Fecha o scanner para evitar vazamentos de recursos
            terminal.close();
        }
    }
    
    /**
     * Método que realiza a contagem baseada nos parâmetros fornecidos.
     * 
     * @param parametroUm O primeiro parâmetro inteiro fornecido pelo usuário.
     * @param parametroDois O segundo parâmetro inteiro fornecido pelo usuário.
     * @throws ParametrosInvalidosException Se o segundo parâmetro não for maior que o primeiro.
     */
    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        // Validar se parametroUm é MAIOR que parametroDois e lançar a exceção
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException("O segundo parâmetro deve ser maior que o primeiro");
        }
        
        int contagem = parametroDois - parametroUm;
        // Realizar o for para imprimir os números com base na variável contagem
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo o número " + i);
        }
    }
}

```

## Como utilizar o Projeto

1. Compilação
* Navegue até o diretório do projeto onde os arquivos ParametrosInvalidosException.java e Contador.java estão localizados.
* Compile os arquivos Java utilizando o comando:
```
javac ParametrosInvalidosException.java Contador.java
```
2. Execução
* Execute a classe Contador utilizando o comando:
```
java Contador
```
3. Entrada do Usuário
* Quando solicitado, insira o primeiro e o segundo parâmetro (números inteiros).
* O programa irá então realizar a contagem conforme especificado e imprimir os resultados no console.

4. Tratamento de Exceções
* Se o primeiro parâmetro for maior ou igual ao segundo, o programa lançará a exceção ParametrosInvalidosException e exibirá a mensagem de erro apropriada.

## Exemplos de Uso

* Entrada Válida:
```
Digite o primeiro parâmetro
5
Digite o segundo parâmetro
10
```
* Saída:
```
Imprimindo o número 1
Imprimindo o número 2
Imprimindo o número 3
Imprimindo o número 4
Imprimindo o número 5
```
* Entrada inválida
```
Digite o primeiro parâmetro
15
Digite o segundo parâmetro
10
```
* Saída:
```
O segundo parâmetro deve ser maior que o primeiro
```

## Considerações Finais
Este projeto foi desenvolvido para demonstrar o uso de exceções customizadas e a lógica de controle de fluxo em Java. A estrutura modular facilita a manutenção e a expansão do código conforme necessário.
