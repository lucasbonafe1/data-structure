## Tabela de disperção


Uma tabela hash é uma estrutura de dados que associa chaves a valores, usando uma função hash para calcular um índice em um array onde o valor pode ser rapidamente armazenado ou recuperado. O objetivo principal é permitir operações de inserção, busca e exclusão de dados de forma muito eficiente, sendo comum em dicionários, mapas e sistemas de autenticação. 
<img width="1023" height="574" alt="image" src="https://github.com/user-attachments/assets/746875e4-8514-4373-bc18-0fbaf9825124" />

### Como funciona
- **Chave-valor**: A tabela armazena pares de informações, onde cada chave é única e associada a um valor.
- **Função hash**: Uma função especial, chamada função de dispersão (ou função hash), é usada para converter a chave em um número inteiro. Esse número se torna o índice no array da tabela onde o valor correspondente será armazenado, **mas** caso a posição resultante do calculo já estiver ocupada, o hash pula de posição até encontrar uma vazia.
- **Armazenamento**: Ao inserir um item, a chave é passada pela função hash para encontrar seu índice. O valor é então armazenado naquela posição.
- **Recuperação**: Para encontrar um valor, a chave é novamente passada pela função hash. O sistema vai diretamente para o índice calculado e recupera o valor associado, sem precisar percorrer toda a estrutura. 

### Exemplos de uso
- **Dicionários e mapas**: Em programação, muitas linguagens usam tabelas hash para implementar estruturas de dados de dicionários ou mapas, onde você pode armazenar e acessar informações usando uma chave.
- **Autenticação de usuários**: Um sistema pode armazenar um hash da senha de um usuário em vez da própria senha. Ao fazer login, o sistema calcula o hash da senha digitada e compara com o valor armazenado para verificar a autenticidade.
- **Assinaturas digitais**: Elas usam funções hash para garantir a integridade e autenticidade de documentos, verificando se o hash do documento corresponde ao hash original. 
