# -Lab-5
Теорія Алгоритмів Lab 5

#include <stdio.h>
#include <stdlib.h>
void transformArray(int *arr, int size) {  
    int minIndex = 0;
    int maxIndex = 0;
    for (int i = 1; i < size; i++) {
        if (arr[i] < arr[minIndex]) { 
            minIndex = i;
        }
        if (arr[i] > arr[maxIndex]) {
            maxIndex = i;
        }
    }
    int temp = arr[0];
    arr[0] = arr[minIndex];
    arr[minIndex] = temp;
    temp = arr[size - 1];
    arr[size - 1] = arr[maxIndex];
    arr[maxIndex] = temp;
}
int main() {
    int size;
    printf("Введіть розмір масиву: ");
    scanf("%d", &size);   
    int *array = (int*) malloc(size * sizeof(int));
    if (array == NULL) {
        printf("Помилка виділення пам'яті.\n");
        return 1;
    }   
    printf("Введіть елементи масиву:\n");
    for (int i = 0; i < size; i++) {
        scanf("%d", &array[i]);
    }  
    printf("Початковий масив: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", array[i]);
    }
    printf("\n"); 
    transformArray(array, size); 
    printf("Перетворений масив: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", array[i]);
    }
    printf("\n");   
    free(array);   
    return 0;
}
