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
