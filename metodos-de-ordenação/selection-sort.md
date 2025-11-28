# Selection Sort

A ordenação por seleção (do inglês, selection sort) é um algoritmo de ordenação baseado em se passar sempre o menor valor do vetor para a primeira posição (ou o maior dependendo da ordem requerida), depois o de segundo menor valor para a segunda posição, e assim é feito sucessivamente com os n − 1 elementos restantes, até os últimos dois elementos.

## Descrição do algoritmo
É composto por dois laços, um laço externo e outro interno. O laço externo serve para controlar o índice inicial e o interno percorre todo o vetor. Na primeira iteração do laço externo o índice começa de 0 e cada iteração ele soma uma unidade até o final do vetor e o laço mais interno percorre o vetor começando desse índice externo + 1 até o final do vetor.

## Código
```bash
public static void selectionSort() {
  int arr[] = {12, 5, 6, 2, 4, 7, 99, 24};

  for (int i = 0; i < arr.length - 1; i++) {
      int minIndex = i; // índice do menor valor encontrado

      for (int j = i + 1; j < arr.length; j++) {
          if (arr[j] < arr[minIndex]) {
              minIndex = j; // atualiza o menor encontrado
          }
      }

      // troca se achar um menor
      if (minIndex != i) {
          int temp = arr[i];
          arr[i] = arr[minIndex];
          arr[minIndex] = temp;
      }
  }

  for (int n : arr) {
      System.out.println(n);
  }
}
```
