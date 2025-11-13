## Fila

É uma estrutura linear com dois lados de acesso, sendo que a inserção só é possível por um dos lados, e a remoção pelo outro, e possui uma capacidade máxima. Estruturas de filas seguem o modelo FIFO (First In First Out), em que o primeiro a entrar na lista (mais antigo), é o primeiro a sair.

![alt text](image.png)
O lado de saída é chamado de início e o lado de entrada é chamado de fim.

- inserção de um item -> enqueue(item)
- extração de um item -> desenqueue()

### O enfileiramento de elementos sempre ocorre quando:
- O servidor está indisponível e elementos precisam ser processados para passar pra outra etapa.

- O servidor está disponível, mas a taxa de chegada de elementos é maior que a capacidade de processamento do servidor.

### Buffer circular
Um buffer circular é um array que se comporta como uma fila infinita, mas que reutiliza o mesmo espaço quando chega ao fim, “voltando” para o começo.

🔁 Como ele funciona:

Ele usa dois ponteiros:

- **inicio**: saída da fila (remover);

- **fim**: entrada de dados na fila (adicionar). 

Quando você adiciona algo:

<pre>
    fim = (fim + 1) % capacidade
</pre>

- Após setado o valor de fim aponta para a próxima posição livre (Antes do cálculo, ele é referente ao item mais recente adicionado a lista)

_“% capacidade” garante que o índice volte ao início quando chegar ao final._

#### Resumo
 É utilizado quando é preciso armazenar dados temporários de forma contínua, mas sem precisar:

- mover elementos dentro de um array,

- nem aumentar o tamanho da estrutura.

Ou seja, quando é necessário uma **fila eficiente e de tamanho fixo**, que nunca cresce e **reaproveita o espaço automaticamente**.
### Tipagem em Java
_public Queue<> fila;_