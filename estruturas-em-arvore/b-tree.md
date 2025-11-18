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

--------------------------------------------------------------------------------------

# Árvore B+

A árvore B+ é uma variação da árvore B, projetada para melhorar a eficiência de operações de busca, inserção e remoção de chaves. Nela, todas as chaves são armazenadas nos nós folha, enquanto os nós internos contêm apenas ponteiros para os nós folha. Isso permite um acesso sequencial mais eficiente às chaves, pois todos os nós folha estão interligados, facilitando a varredura de dados. 

## Vantagens da Árvore B+
- Eficiência em Busca: A estrutura permite buscas rápidas, pois as chaves nos nós internos direcionam a busca para o nó folha correto, onde os dados estão armazenados.
- Menor Número de Acessos a Disco: Como as árvores B+ são projetadas para minimizar o número de acessos a disco, elas são ideais para sistemas que lidam com grandes volumes de dados, como bancos de dados e sistemas de arquivos. 
- Facilidade de Inserção e Remoção: A inserção e remoção de chaves são realizadas nos nós folha, e se um nó ficar cheio, ele pode ser dividido, mantendo a árvore balanceada. 
