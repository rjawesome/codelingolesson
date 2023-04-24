# Sorting


## Insertion Sort
A simple sorting algorithm that works similar to the way you sort playing cards in your hands. The array is virtually split into a sorted and an unsorted part. Values from the unsorted part are picked and placed at the correct position in the sorted part.


## Selection Sort
The algorithm repeatedly selects the min (or max) element from the unsorted part of the list and swaps it with the first element of the unsorted part until the entire list is sorted. The algorithm maintains two subarrays in a given array: the subarray which already sorted and the remaining subarray was unsorted. In every iteration of the selection sort, the min element is picked and moved to the beginning of the sorted subarray. After every iteration sorted subarray size increase by one and the unsorted subarray size decrease by one.


## What is Heap Sort?
Heap Sprt is a comparison-based sorting technique based on Binary Heap data structure. It is similar to the selection sort where we first find the minimum element and place the minimum element at the beginning. Repeat the same process for the remaining elements. This algorithm uses the function heapSort() to construct the max heap initially for use. Once done, every root element is extracted and sent to the end of the array. The root is again extracted and sent to the end of the array, repeating again. The sort also uses the function heapify() to determine the maximum from the element being examined as the root and its two children. If the maximum is among the children of the root, the root and its child are swapped. When the maximum element in the array is found the function stops.

Example of heap sort implementation from GeekforGeeks:

```
// Java program for implementation of Heap Sort
public class HeapSort {
    public void sort(int arr[])
    {
        int n = arr.length;
 
        // Build heap (rearrange array)
        for (int i = n / 2 - 1; i >= 0; i--)
            heapify(arr, n, i);
 
        // One by one extract an element from heap
        for (int i = n - 1; i >= 0; i--) {
            // Move current root to end
            int temp = arr[0];
            arr[0] = arr[i];
            arr[i] = temp;
 
            // call max heapify on the reduced heap
            heapify(arr, i, 0);
        }
    }
 
    // To heapify a subtree rooted with node i which is
    // an index in arr[]. n is size of heap
    void heapify(int arr[], int n, int i)
    {
        int largest = i; // Initialize largest as root
        int l = 2 * i + 1; // left = 2*i + 1
        int r = 2 * i + 2; // right = 2*i + 2
 
        // If left child is larger than root
        if (l < n && arr[l] > arr[largest])
            largest = l;
 
        // If right child is larger than largest so far
        if (r < n && arr[r] > arr[largest])
            largest = r;
 
        // If largest is not root
        if (largest != i) {
            int swap = arr[i];
            arr[i] = arr[largest];
            arr[largest] = swap;
 
            // Recursively heapify the affected sub-tree
            heapify(arr, n, largest);
        }
    }
 
    /* A utility function to print array of size n */
    static void printArray(int arr[])
    {
        int n = arr.length;
        for (int i = 0; i < n; ++i)
            System.out.print(arr[i] + " ");
        System.out.println();
    }
 
    // Driver program
    public static void main(String args[])
    {
        int arr[] = { 12, 11, 13, 5, 6, 7 };
        int n = arr.length;
 
        HeapSort ob = new HeapSort();
        ob.sort(arr);
 
        System.out.println("Sorted array is");
        printArray(arr);
    }
}
HeapSort.main(null);
```

```
Sorted array is
5 6 7 11 12 13 
```


## Sorting Hack: 
Write a insertion or selection sort program that sorts an ArrayList<Country> in decreasing order so that the largest country is at the beginning of the array (Create your own Country class with size). Use a Comparator.
### Bonus Hack:
Use heap sort to do the above