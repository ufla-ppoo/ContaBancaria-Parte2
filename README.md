# Conta Bancaria - Parte 2

Este exercício tem como objetivo trabalhar o conceito de Coleções em Java.
Ele é uma continuação de um exercício anterior ([Conta Bancaria](https://github.com/ufla-ppoo/ContaBancaria)).

## Orientações Gerais

- Você deve fazer um passo de cada vez, testá-lo, fazer o commit e enviar suas alterações.
Somente depois disso é que você deve passar para o próximo passo.

- **ATENÇÃO**: **desligue o GitHub Copilot para fazer o exercício!**
  - Se você utilizá-lo você não estará realmente exercitando os conceitos aprendidos e
    não terá o domínio adequado para desenvolver as habilidades necessárias para se tornar
	um bom programador/desenvolvedor.
  - Sem contar ainda a questão do plágio.
  - Lembre-se que você pode (e deve) consultar os materiais da disciplina para fazer o exercício.

- Esse arquivo README pode ser melhor visualizado no VS Code (com formatação adequada) 
  abrindo-o no modo de visualização. Para isso, basta apertar Ctrl+Sfhit+V com ele aberto.

## Passo 0 - Código do exercício anterior

Neste passo, você deverá pegar o código do exercício anterior de conta bancária e utilizá-lo como o código inicial deste exercício.
Para isso, basta copiar os arquivos de extensão `.java` do exercício anterior para a pasta `src` deste projeto.

Observação: caso você não tenha feito todos os passos do exercício anterior, é necessário fazer isso agora, para que consiga fazer os passos abaixo.

## Passo 1 - Coleção de Contas

No exercício anterior, ao tratar várias contas, foi pedido para que você criasse uma 
coleção de contas, e o enunciado dizia que poderia ser um vetor ou um `ArrayList`. 
Agora, neste exercício, caso você tenha usado um vetor, você deve substituí-lo por um `ArrayList` de contas.

## Passo 2 - Remoção de Contas

Vamos agora adicionar uma nova opção no menu do nosso programa para que o usuário consiga remover uma conta da lista.

- O usuário deverá informar o número da conta a ser removida.
- A conta só poderá ser removida se o seu saldo for igual a zero.

  - Se tiver dinheiro na conta, deve ser exibida uma mensagem para o usuário dizendo que não é possível cancelar contas com saldo disponível.
  - Se a conta estiver usando o limite (ou seja, tiver saldo negativo), deve ser exibida mensagem dizendo que não é possível cancelar contas em débito.
  - Se a conta tiver saldo igual a zero, a mesma deve ser removida, e uma mensagem adequada deve ser exibida para o usuário.

## Passo 3 - Filtrar contas pelo nome do cliente

Agora vamos adicionar uma nova opção de menu para filtrar as contas de acordo com o nome do cliente.
Esta opção deve funcionar da seguinte forma:

- O usuário deverá informar uma string com o nome (ou parte do nome) de um cliente.
- O programa exibirá então os dados (número da conta e nome do cliente) das contas que tenham o nome (ou a parte do nome) informada pelo usuário.

Exemplo:

Suponha que existam as seguintes contas (números de conta e nomes de clientes):

```text
1000 - João da Silva
1001 - Joaquim Ferreira
1002 - Maria Pereira
1003 - Pedro José
```

E suponha que o usuário informe a string `"Jo"`.

- Nesse caso, deverão ser exibidos os dados das contas 1000, 1001 e 1003, pois em todas elas os nomes dos clientes possuem a substring `"Jo"`.

> **Dica 1: método `contains`**
> 
> A classe String do Java possui um método chamado `contains` que indica se uma string possui uma determinada substring.
> O programa abaixo ilustra a utilização de tal método.
> Experimente implementá-lo em seu computador.
> 
> ```java
> Scanner entrada = new Scanner(System.in);
> 
> System.out.println("Digite uma frase:");
> String frase = entrada.nextLine();
> 
> System.out.println("Digite uma palavra:");
> String palavra = entrada.nextLine();
> 
> if (frase.contains(palavra)) {
>     System.out.println("Palavra existe na frase");
> }
> else {
>     System.out.println("Palavra não encontrada!");
> }
> ```

## Passo 4 - Melhorando filtro de contas pelo nome do cliente

No passo anterior, se o usuário digitasse `"jo"`, nenhuma conta seria exibida.
Mas seria bem mais prático para o usuário se ele não precisasse se preocupar em acertar
se as letras são maiúsculas ou minúsculas na hora de fazer o filtro.
Neste passo você deve permitir que o usuário digite uma substring sem se preocupar com isso.

Para isso, faça uma busca na internet por métodos da classe `String` do Java que convertam strings para minúsculo/maiúsculo, ou que comparem strings ignorando essa questão.
Utilize então o(s) método(s) pesquisado(s) para permitir que o usuário possa informar a parte do
nome do cliente de qualquer forma (tudo maiúsculo, tudo minúsculo ou misturado) e sejam exibidas
todas as contas que tenham aquela substring ignorando se as letras são maiúsculas ou minúsculas.


## Passo 5 - Remoção de várias contas com iteradores

Vamos agora adicionar uma nova opção no menu do nosso programa para que o usuário consiga 
remover várias contas da lista.

- O usuário deverá informar o nome, ou parte do nome, do cliente.
- Deverão ser removidas todas as contas cujo nome do cliente tenham a substring informada 
  (ignorando maiúsculas e minúsculas) e que tenham saldo igual a zero.
  - Para cada conta que tenha a parte do nome do cliente deve ser informado ao usuário se a conta foi 
    removida ou não, de forma similar ao que foi feito no passo 2.
- Na implementação, você **deve utilizar iteradores** para buscar as contas a serem removidas.

## Passo 6 - Ordenando as contas

Vamos agora adicionar uma nova opção no menu do nosso programa para que o usuário possa
ordenar as contas da coleção.

- O usuário deverá escolher se quer ordenar as contas pelo número da conta, pelo nome ou pelo saldo.
- Em seguida, as contas devem ser exibidas de acordo com a opção escolhida.
