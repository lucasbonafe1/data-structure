## Merge Sort

Merge Sort é um algoritmo eficiente de ordenação por divisão e conquista. Se nossa missão é ordenar um array comparando seus elementos, do ponto de vista assintótico, n∗logn é o nosso limite inferior. Ou seja, nenhum algoritmo de ordenação por comparação é mais veloz do que n∗logn. Formalmente, todos são Ω(n∗logn)

No caso do Merge Sort, uma característica importante é que sua eficiência é n∗logn para o melhor, pior e para o caso médio. Isso nos dá uma garantia de que, independente da disposição dos dados em um array, a ordenação será eficiente.

## Como funciona
Merge é a rotina que combina dois arrays ordenados em um outro também ordenado. Na prática, não queremos ficar criando arrays separados para uni-los. Isso custa memória e processamento, pois a cada array criado temos que transferir os elementos do array original para ele. 

O que fazemos então é organizar os dados no array a ser ordenado de forma que uma parte dele esteja ordenada e outra também. Assim, no Merge Sort não fazemos o merge de dois arrays, mas fazemos o merge de duas partes ordenadas de um mesmo array.

![merge-sort](https://github.com/user-attachments/assets/1005b3d1-b286-48cb-b305-39451a6ec7dd)

## Código
    public static void mergeSort(int[] arr, int left, int right) {
        // Caso base: se o array tiver um único elemento, ele já está ordenado
        if (left < right) {
            // Encontra o ponto médio do array
            int mid = left + (right - left) / 2;

            // Chama recursivamente para ordenar a primeira metade
            mergeSort(arr, left, mid);
            // Chama recursivamente para ordenar a segunda metade
            mergeSort(arr, mid + 1, right);

            // Combina as duas metades ordenadas
            merge(arr, left, mid, right);
        }
    }

    // Função para combinar (intercalar) dois sub-arrays ordenados
    public static void merge(int[] arr, int left, int mid, int right) {
        // Encontra o tamanho dos dois sub-arrays a serem mesclados
        int size1 = mid - left + 1;
        int size2 = right - mid;

        // Cria arrays temporários
        int[] leftArray = new int[size1];
        int[] rightArray = new int[size2];

        // Copia os dados para os arrays temporários
        for (int i = 0; i < size1; i++) {
            leftArray[i] = arr[left + i];
        }
        for (int j = 0; j < size2; j++) {
            rightArray[j] = arr[mid + 1 + j];
        }

        // Índices iniciais para os sub-arrays temporários e o array principal
        int i = 0, j = 0;
        int k = left; // Índice inicial do array principal

        // Intercala os elementos dos arrays temporários de volta para o array principal
        while (i < size1 && j < size2) {
            if (leftArray[i] <= rightArray[j]) {
                arr[k] = leftArray[i];
                i++;
            } else {
                arr[k] = rightArray[j];
                j++;
            }
            k++;
        }

        // Copia os elementos restantes de leftArray[], se houver
        while (i < size1) {
            arr[k] = leftArray[i];
            i++;
            k++;
        }

        // Copia os elementos restantes de rightArray[], se houver
        while (j < size2) {
            arr[k] = rightArray[j];
            j++;
            k++;
        }
    }

    // Função auxiliar para imprimir o array
    public static void printArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    // Exemplo de uso
    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};
        System.out.println("Array original:");
        printArray(arr);

        // Chama o método mergeSort para ordenar o array
        mergeSort(arr, 0, arr.length - 1);

        System.out.println("\nArray ordenado:");
        printArray(arr);
    }

