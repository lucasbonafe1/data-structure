# Bubble Sort

É um algoritmo de ordenação simples que funciona comparando repetidamente elementos adjacentes e trocando suas posições se estiverem na ordem errada. Esse processo é repetido até que a lista inteira esteja ordenada.

Por isso o nome Bubble Sort, pois as mudanças tem um comportamento semelhante ao de bolhas (Os números vão sendo ordenados e mudam de posição)

## Como Funciona (Passo a Passo)
O algoritmo percorre a lista várias vezes. Em cada passagem, o maior (ou menor, dependendo da ordem desejada) elemento "borbulha" para sua posição final correta na extremidade da lista. 
- Comparação: O algoritmo começa comparando o primeiro par de elementos adjacentes.
- Troca: Se o primeiro elemento for maior que o segundo (para ordenação crescente), eles são trocados de posição. Caso contrário, permanecem como estão.
- Iteração Interna: O processo de comparação e troca continua para o próximo par adjacente e assim sucessivamente, até o final da lista. Ao final da primeira passagem, o maior elemento estará garantidamente na última posição.
- Iteração Externa: O algoritmo repete as passagens, mas a cada nova iteração, o número de elementos a serem verificados diminui em um, pois os elementos no final da lista já estão ordenados.
- Conclusão: O processo termina quando uma passagem completa pela lista ocorre sem realizar nenhuma troca, indicando que o vetor está totalmente ordenado.
 
## Complexidade e Eficiência
A principal desvantagem do Bubble Sort é sua baixa eficiência para grandes conjuntos de dados. 
- Pior Caso e Caso Médio: A complexidade de tempo é O(n²), onde n é o número de elementos. Isso significa que o tempo de execução cresce quadraticamente com o tamanho da entrada.
- Melhor Caso: Se a lista já estiver ordenada, uma versão otimizada do algoritmo pode detectar isso em apenas uma passagem, resultando em uma complexidade de tempo linear de O(n).
- Complexidade de Espaço: O algoritmo é in-place, ou seja, não requer memória adicional significativa, tendo complexidade de espaço O(1).

  ## Código
```bash
  public static void bubbleSort(){
	    int[] arr = {7, 3, 9, 5, 78, 6, 100, 10, 1, 74, 120};
	    
	    int length = arr.length;
	    int aux; // Para setar o valor do elemento antigo no próximo
	    
	    // Este for controla o número total de "passagens" pela lista. (Pra sempre que não tenha finalizado a ordenação, voltar do início e continuar o processo)
	    for (int i = 0; i < length - 1; i++){
	        // E esse segundo itera sobre os elementos internos do array
          // (length - i) para não realizar comparações com elementos do final da lista já ordenados
	        for (int j = 0; j < (length - i) - 1; j++){
	            if (arr[j] > arr[j + 1]){
	                aux = arr[j];
	                arr[j] = arr[j + 1];
	                arr[j + 1] = aux;
	            } 
	        }    
	    } 
}
```
