# Quick Sort

O Quicksort é um algoritmo de ordenação eficiente baseado no paradigma de dividir para conquistar. Criado por Tony Hoare em 1962, ele organiza os elementos de um vetor ao particioná-lo em duas partes e ordená-las recursivamente. Sua principal vantagem é ser um algoritmo in-place, ou seja, não requer memória adicional significativa.

## Funcionamento do Quicksort

O algoritmo segue os seguintes passos:

- Escolhe um elemento como pivô (pode ser o primeiro, último ou um elemento aleatório do vetor).

- Reorganiza o vetor de forma que todos os elementos menores ou iguais ao pivô fiquem à esquerda e os maiores à direita.

- Aplica o Quicksort recursivamente nas duas partições (esquerda e direita).

![quick_sort_partition_animation](https://github.com/user-attachments/assets/4e14540f-8a5f-46f8-8d6a-06f5be5472aa)

## Vantagens e Desvantagens

O Quicksort é geralmente mais rápido que outros algoritmos de ordenação, como o Merge Sort, devido à menor sobrecarga de memória. No entanto, seu desempenho pode ser prejudicado no pior caso, especialmente se o pivô for escolhido de forma inadequada.

## Código

```bash
 // Método principal para executar o QuickSort
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            // Encontra o índice do pivô após a partição
            int pivotIndex = partition(arr, low, high);

            // Ordena recursivamente as duas metades
            quickSort(arr, low, pivotIndex - 1);
            quickSort(arr, pivotIndex + 1, high);
        }
    }

    // Função de partição (Lomuto Partition Scheme)
    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high]; // Escolhe o último elemento como pivô
        int i = low - 1; // Índice do menor elemento

        for (int j = low; j < high; j++) {
            if (arr[j] <= pivot) {
                i++;
                swap(arr, i, j);
            }
        }

        // Coloca o pivô na posição correta
        swap(arr, i + 1, high);
        return i + 1;
    }

    // Método auxiliar para trocar elementos
    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Digite o tamanho do array: ");
            int n = scanner.nextInt();

            if (n <= 0) {
                System.out.println("O tamanho do array deve ser maior que zero.");
                return;
            }

            int[] arr = new int[n];
            System.out.println("Digite os elementos do array:");
            for (int i = 0; i < n; i++) {
                arr[i] = scanner.nextInt();
            }

            System.out.println("Array original: " + Arrays.toString(arr));

            quickSort(arr, 0, arr.length - 1);

            System.out.println("Array ordenado: " + Arrays.toString(arr));

        } catch (InputMismatchException e) {
            System.out.println("Entrada inválida. Digite apenas números inteiros.");
        } finally {
            scanner.close();
        }
    }
```
