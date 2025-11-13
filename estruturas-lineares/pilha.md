## Pilha

As pilhas funciona como em cenários reais, em que um item e adicionado pelo topo e o primeiro a ser removido também é ele. Na programação, é possível pensar como o item mais recente a entrar na estrutura, também será o primeiro a sair, seguindo o modelo LIFO (Last In First Out).

A retirada ou inserção de um elemento no meio da pilha requer a necessidade de algum tipo de mecanimos para "levantar" os items que estão acima, para adiciona-lo. No modelo clássico do TAD Pilha, não é previsto essa operação.

- inserção de um item -> push(obj)
- remoção do último item adicionado -> pop()

### Tipagem em Java
_public int[] pilha;_