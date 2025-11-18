# Árvore binária

Uma árvore binária é uma estrutura de dados hierárquica composta por nós, onde cada nó pode ter no máximo dois filhos: um à esquerda e outro à direita.

<img width="373" height="291" alt="image" src="https://github.com/user-attachments/assets/bdce98eb-ba6a-4151-a544-f5dc872ae8b3" />

## Operações Básicas

### Inserção

A inserção começa no nó raiz e desce recursivamente até encontrar a posição correta. Se o valor for menor que o nó atual, move-se para a subárvore esquerda; caso contrário, para a direita.

### Busca

A busca segue o mesmo princípio da inserção, comparando o valor desejado com os nós da árvore até encontrá-lo ou atingir um nó nulo.

### Remoção

A remoção pode ser mais complexa, pois envolve três casos:

- O nó não tem filhos: basta removê-lo.
- O nó tem um filho: substitui-se o nó pelo seu filho.
- O nó tem dois filhos: substitui-se pelo sucessor em ordem (menor valor da subárvore direita).
