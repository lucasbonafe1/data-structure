# Grafos

É um conjunto de elementos interconectados de forma matricial, podendo um elemento ter relações com todos os outros elementos ou só apenas com um.

Cada elemento é denominado de "**Vértice**" e cada conexão é chamada de "**Aresta**"

<img width="570" height="286" alt="grafos" src="https://github.com/user-attachments/assets/245853ce-bbca-4c89-94c8-63a5521f31df" />

## Tipos de grafos
- Grafo direcionado (digraph) → A → B é diferente de B → A
- Grafo não direcionado → Conexões bidirecionais
- Grafo ponderado → arestas têm peso (distância, custo)
- Grafo completo → todo mundo conectado com todo mundo
- Grafo cíclico / acíclico → importante em detecção de dependências
- DAG (Directed Acyclic Graph)
  - pipelines
  - versionamento (Git)
  - sistemas de build
  - ordenação topológica

## Como são utilizados
Os grafos são utilizados em sistemas como:
- Relacionamentos de amigos/seguidores em redes sociais
- GPS, em que cada cidade é um vértice e cada rua é uma aresta
- Redes de computadores, por exemplo Internet
- Redes de abastecimento de água ou redes de energia elétrica

## Tipos de busca
Quando falamos em realizar uma busca em um grafo, basicamente estamos dizendo que iremos percorrer as arestas do grafo de forma sistemática, passando pelos vértices.

### Depth-First Search (DFS)

![1_aApu4NMQukGtjySD1lvbsw](https://github.com/user-attachments/assets/6204004d-b9d6-4af8-ab71-72782b7f8076)

#### Lógica de Funcionamento
Primeiramente, definimos um nó inicial. Começamos aí com o Nó 1. Enquanto este nó não for num nó final, e por nó final eu quero dizer um nó onde todas as adjacências já tenham sido visitadas, escolhemos um dos adjacentes não visitado e o visitamos (Por isso o nome, busca em profundidade).

No exemplo, ele começa no Nó 1 (marcando-o como visitado) e vê todas as suas adjacências: Nó 2, Nó 5 e Nó 3. Ele vai para o Nó 2 (marcando-o como visitado) e e olha para todas as adjacências dele: Nó 6 e Nó 4. A partir daí, ele vai para o Nó 6 (marcando-o como visitado) e olha para suas adjacências: Nó 2. Como o Nó 2 já foi visitado, ele vai para a outra adjacência de Nó 2 que não foi visitada (Nó 4, marcando-o como visitado).

Se o nó que estamos observando tiver pai, voltamos ao pai dele. Se não tiver pai, mas se tiver um nó não visitado, escolhemos outro nó não visitado.

### Breadth-First Search (BFS)

![1_PvXMyl7PHuW8GAszMlYKZQ](https://github.com/user-attachments/assets/f7e954df-52fd-4b79-ba4a-f00f90ec557b)

#### Lógica de Funcionamento
Em um primeiro momento, iremos definir o nó inicial, marcar como visitado e adicioná-lo à fila. No caso, começamos pelo Nó 1. Lembre-se de que uma fila tem como característica que o primeiro elemento a entrar é o primeiro a sair (FIFO, First In, First Out).

Depois disso, enquanto a fila não estiver vazia, removemos o primeiro nó da fila (chamaremos esse nó de u) e para cada v de u, se v não foi explorado, marcamos v como explorado e o adicionamos à fila. Repetimos isso de outro nó inicial se houver.

No caso da Imagem 5, começamos com o Nó 1 na fila. Depois, vemos quem são os vizinhos do Nó 1 (que são os nós 2, 5 e 3) e os adicionamos na fila. Repetimos o processo até que não haja mais nós a serem explorados.
Comparação entre BFS e DFS


###  Vantagens e desvantagens de cada um dos métodos para situações específicas.

- Quando estamos trabalhando com grafos densos, o **BFS** pode ser mais eficiente. Além disso, usamos o **BFS** comumente em problemas onde queremos saber qual o caminho mínimo de arestas entre um vértice e qualquer um outro.
- Há desvantagens em usar o **BFS** quando o grafo for esparso, com a relação próxima de 0, que acaba sendo menos eficiente. Além disso, requer mais espaço de armazenamento para fila de vértices.
- Já o **DFS** é bastante útil quando queremos encontrar o total de caminhos de um ponto X a um ponto Y ou encontrar ciclos, e pode ser mais eficiente em grafos esparsos, onde aquela relação é próxima de zero.
----------------------------------------------------------------------------------------------------
