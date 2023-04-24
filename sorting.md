# Sorting


## Insertion Sort
A simple sorting algorithm that works similar to the way you sort playing cards in your hands. The array is virtually split into a sorted and an unsorted part. Values from the unsorted part are picked and placed at the correct position in the sorted part.
```
public class InsertionSort {
    public void sort(int arr[]) {
        for (int i = 1; i < arr.length; ++i) {
            int key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key;
        }
    }
    public static void main() {
        InsertionSort ob = new InsertionSort();
        int arr[] = {1,7,23,6,4,6,1};
        ob.sort(arr);
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
    }
}
InsertionSort.main();
```
```
1 1 4 6 6 7 23 
```

## Selection Sort
The algorithm repeatedly selects the min (or max) element from the unsorted part of the list and swaps it with the first element of the unsorted part until the entire list is sorted. The algorithm maintains two subarrays in a given array: the subarray which already sorted and the remaining subarray was unsorted. In every iteration of the selection sort, the min element is picked and moved to the beginning of the sorted subarray. After every iteration sorted subarray size increase by one and the unsorted subarray size decrease by one.
```
public class SelectionSort {
    public void sort(int arr[]) {
        for (int i = 0; i < arr.length-1; i++) {
            int min_idx = i;
            for (int j = i+1; j < arr.length; j++) {
                if (arr[j] < arr[min_idx])
                    min_idx = j;
            }
            int temp = arr[min_idx];
            arr[min_idx] = arr[i];
            arr[i] = temp;
        }
    }
    public static void main() {
        SelectionSort ob = new SelectionSort();
        int arr[] = {1,7,23,6,4,6,1};
        ob.sort(arr);
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
    }
}
InsertionSort.main();
```
```
1 1 4 6 6 7 23 
```

## Heap Sort
Heap sort is a comparison-based sorting technique based on Binary Heap data structure. It is similar to the selection sort where we first find the minimum element and place the minimum element at the beginning. Repeat the same process for the remaining elements. This algorithm uses the function heapSort() to construct the max heap initially for use. Once done, every root element is extracted and sent to the end of the array. The root is again extracted and sent to the end of the array, repeating again. The sort also uses the function heapify() to determine the maximum from the element being examined as the root and its two children. If the maximum is among the children of the root, the root and its child are swapped. When the maximum element in the array is found the function stops.


## Sorting Hack: 
Write a insertion or selection sort program that sorts an ArrayList<Country> in decreasing order so that the largest country is at the beginning of the array (Create your own Country class with size). Use a Comparator.
### Bonus Hack:
Use heap sort to do the above