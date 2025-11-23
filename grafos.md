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
- DAG (Directed Acyclic Graph) → MUITO usado em programação
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
