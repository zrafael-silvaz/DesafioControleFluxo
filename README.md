# Classe Contador

A classe `Contador` é uma classe Java que permite ao usuário inserir dois parâmetros inteiros e, em seguida, realiza uma contagem do intervalor do primeiro parâmetro até o segundo parâmetro. 
Se o segundo parâmetro for menor que o primeiro, a classe lançará uma exceção `ParametrosInvalidosException` para indicar que o segundo parametro deve ser maior que o primeiro.

## Código

```java
public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();

        try {
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException exception) {
            System.err.println("O segundo parâmetro deve ser maior que o primeiro");
        }
    }

    static void contar(int parametroUm, int parametroDois ) throws ParametrosInvalidosException {
        if (parametroUm > parametroDois)
            throw new ParametrosInvalidosException();
        int contagem = parametroDois - parametroUm;
        for (int i = 1; i <= contagem; i++) {
            System.out.printf("Imprimindo o número %d\n",i);
        }
    }
}
```
