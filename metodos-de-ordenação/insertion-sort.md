# Insertion Sort

O insertion sort funciona comparando cada elemento com os elementos anteriores, e inserindo-o na posição correta na lista ordenada.

## A ideia por trás do Insertion Sort
A ideia por trás do Insertion Sort é semelhante a como organizamos cartas em um baralho. Ao recebermos uma nova carta, a comparamos com as cartas existentes e a inserimos na posição correta de acordo com sua ordem. Da mesma forma, o Insertion Sort compara cada elemento da lista com os elementos anteriores, encontrando o local adequado para inseri-lo.

## Complexidade de Tempo
| Caso          | Complexidade | Explicação                                                         |
|---------------|--------------|---------------------------------------------------------------------|
| Melhor caso   | O(n)         | Ocorre quando o array já está ordenado. Apenas uma comparação por elemento. |
| Caso médio    | O(n²)        | Em média, cada elemento precisa ser comparado e deslocado metade das posições anteriores. |
| Pior caso     | O(n²)        | Ocorre quando o array está em ordem inversa, exigindo o máximo de comparações e deslocamentos. |

## Código
```bash
public static void insertionSort(){
	    int[] arr = {12, 1, 3, 5, 2, 6, 7, 11, 9};
	    
	    for (int i = 0; i < arr.length; i++) {
	        int atual = arr[i];
	        for(int j = i - 1; j >= 0; j--){
	            if (atual < arr[j]) {
	                arr[j + 1] = arr[j];
	                arr[j] = atual;
	            }
	        }
	    }
	}
```
