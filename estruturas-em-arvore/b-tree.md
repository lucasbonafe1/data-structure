# Árvore B

Assim como a Árvore binária, possui um nó raiz, que é representado em cima, e os ramos, compostos por outros nós, que se espalham pra baixo.

As diferenças básicas são duas
- Cada nó pode armazenar N elementos (na Binária apenas um)
- Cada nó pode ter até N + 1 filhos (na Binária no máximo dois)

<img width="986" height="337" alt="image" src="https://github.com/user-attachments/assets/303111c7-9ca7-4f17-9de1-5072c2b40d23" />

## Regras de Capacidade e Redistribuição em uma Árvore B

Cada nó deve manter pelo menos a quantidade mínima de chaves, que corresponde a: 
- (ordem da árvore / 2) − 1 (a ORDEM é a capacidade máxima de chaves por nó).

Quando um nó fica abaixo do número mínimo permitido de chaves, ocorre uma operação de restauração, que pode ser:

- **Redistribuição**: o nó empresta uma chave de um nó irmão adjacente que esteja acima da capacidade mínima.

- **Fusão**: caso nenhum irmão tenha chaves suficientes para redistribuição, o nó é fundido com um irmão, e uma chave do nó pai desce para completar essa fusão.

Se um nó é completamente esvaziado e não pode ser restaurado, ele é eliminado, e seus elementos são realocados por meio das operações acima, preservando sempre as propriedades da árvore B.
