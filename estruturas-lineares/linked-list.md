## Lista Ligada

Se trata de um conjunto de elementos do mesmo tipo encadeados de modo que um elemento se liga a outro, possibilitando a formação de uma cadeia.

LinkedList implementa Deque, então tem métodos como **addFirst**, **addLast**, **getFirst**, **getLast**, **push**, **pop**, **poll**, **peek** — facilita usar a mesma estrutura como fila ou pilha.

### Quando usar LinkedList (casos de uso)

Usar LinkedList quando:

- É necessário muitas inserções/remoções em início/fim ou quando estiver manipulando nós frequentemente.

- Implementar fila (FIFO) ou pilha (LIFO) simples e quer métodos sem criar wrappers extras.

- Precisar de uma deque (double-ended queue) onde operações nas 2 pontas precisam ser rápidas.

- Implementar estruturas como lista de nós onde você move um ponteiro/iterador e insere/remove frequentemente.

### Evitar LinkedList quando:

- É preciso de acesso aleatório por índice frequentemente → melhor ArrayList.

- Está buscando melhor localidade de memória e menor overhead por elemento (LinkedList gasta mais memória por nó).
