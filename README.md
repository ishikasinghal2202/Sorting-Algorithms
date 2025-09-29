/*
================================================================================
   SORTING ALGORITHMS PROJECT
================================================================================

>> Aim:
To implement and understand various sorting algorithms using C++, analyze their 
time and space complexities, and compare their performance based on different 
input sizes.

>> Software Used:
- IDE: Code::Blocks / Visual Studio Code / Dev C++
- Compiler: GNU GCC Compiler
- Operating System: Windows/Linux/MacOS
- Language: C++

>> Objectives:
1. To understand the working of popular sorting algorithms such as:
   - Bubble Sort
   - Selection Sort
   - Insertion Sort
   - Merge Sort
   - Quick Sort
2. To implement these algorithms in C++.
3. To analyze and compare their time and space complexity.
4. To visualize and understand flowcharts for sorting mechanisms.
5. To construct tables for performance comparison.

================================================================================
>> Theory:

Sorting is the process of arranging data in a particular order (ascending or 
descending). Efficient sorting is crucial for optimizing the performance of 
other algorithms like search and merge.

Sorting algorithms can be classified based on the following:
- Time Complexity (Best, Average, Worst Case)
- Space Complexity
- Stability (Maintaining relative order of equal elements)
- Method (Comparison-based or non-comparison-based)

--------------------------------------------
| Algorithm     | Time Complexity (Worst) |
|---------------|-------------------------|
| Bubble Sort   | O(n^2)                  |
| Selection Sort| O(n^2)                  |
| Insertion Sort| O(n^2)                  |
| Merge Sort    | O(n log n)              |
| Quick Sort    | O(n^2)                  |
--------------------------------------------

### Bubble Sort (Stable, O(n^2)):
Compares adjacent elements and swaps them if they are in the wrong order. This 
is repeated until the array is sorted.

### Insertion Sort (Stable, O(n^2)):
Builds the sorted list one element at a time by inserting elements in the 
correct position.

### Selection Sort (Unstable, O(n^2)):
Selects the minimum element from the unsorted part and swaps it with the first 
unsorted element.

### Merge Sort (Stable, O(n log n)):
Uses divide-and-conquer to split the array into halves, sort them and then merge.

### Quick Sort (Unstable, O(n^2), Avg O(n log n)):
Uses divide-and-conquer. Picks a pivot and partitions the array around it, 
recursively sorting partitions.

================================================================================
>> Flowchart (for Quick Sort):

                            +--------------------+
                            |   QuickSort(arr)   |
                            +--------------------+
                                      |
                                      v
                          +------------------------+
                          | if (low < high)        |
                          |  partition array       |
                          |  recursively sort      |
                          +------------------------+
                                      |
                          +-----------+-----------+
                          |                       |
                          v                       v
                 QuickSort(arr, low, pi - 1)  QuickSort(arr, pi + 1, high)

>> Table: Quick Sort Time Complexity

-----------------------------------------------
| Case        | Time Complexity | Space       |
|-------------|------------------|-------------|
| Best Case   | O(n log n)       | O(log n)    |
| Average Case| O(n log n)       | O(log n)    |
| Worst Case  | O(n^2)           | O(log n)    |
-----------------------------------------------

================================================================================
>> Algorithm: (Quick Sort - Example)

void quickSort(int arr[], int low, int high) {
    if (low < high) {
        int pivot = partition(arr, low, high);  // partition index
        quickSort(arr, low, pivot - 1);         // sort left sub-array
        quickSort(arr, pivot + 1, high);        // sort right sub-array
    }
}

int partition(int arr[], int low, int high) {
    int pivot = arr[high];  // pivot
    int i = (low - 1);      // index of smaller element

    for (int j = low; j <= high - 1; j++) {
        if (arr[j] < pivot) {
            i++;  // increment index
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i + 1], arr[high]);
    return (i + 1);  // return partition index
}

================================================================================
>> Conclusion:

Through this project, we have implemented and compared multiple sorting 
algorithms. We observed that:

- Simple algorithms like Bubble, Selection, and Insertion are easy to implement 
  but inefficient for large datasets.
- Merge Sort and Quick Sort are more efficient for larger datasets.
- Quick Sort generally outperforms Merge Sort in practical applications, though 
  its worst-case performance is worse.
- Choice of sorting algorithm depends on factors like dataset size, the need for 
  stability, and memory constraints.

================================================================================
*/

