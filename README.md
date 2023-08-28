# Bubble Sort

```flow
Start
|
v
Read unsortedArray
|
v
Is sort needed? --> YES
|                 |
v                 |
Bubble Sort       |
|                 |
v                 |
Print sortedArray |
|                 |
v                 |
End <--------------

```

```flow
Sequence Diagram: Bubble Sort

Actor: Main

Main -> BubbleSort: Call bubbleSort(unsortedArray)
BubbleSort -> BubbleSort: Initialize n = length of array
loop i from 0 to n - 1:
    loop j from 0 to n - i - 1:
        BubbleSort -> Main: Compare arr[j] and arr[j + 1]
        alt arr[j] > arr[j + 1]:
            BubbleSort -> BubbleSort: Swap arr[j] and arr[j + 1]
        end
    end
end
BubbleSort -> Main: Sorted array is ready
Main -> Main: Print sortedArray

```

- java

  ```java
  public class BubbleSort {
      public static void bubbleSort(int[] arr) {
          int n = arr.length;
          for (int i = 0; i < n - 1; i++) {
              for (int j = 0; j < n - i - 1; j++) {
                  if (arr[j] > arr[j + 1]) {
                      int temp = arr[j];
                      arr[j] = arr[j + 1];
                      arr[j + 1] = temp;
                  }
              }
          }
      }

      public static void main(String[] args) {
          int[] unsortedArray = {64, 34, 25, 12, 22, 11, 90};
          bubbleSort(unsortedArray);

          System.out.print("Sorted Array: ", );
          for (int num : unsortedArray) {
              System.out.print(num + " ");
          }
      }
  }

  ```

- javascript

  ```javascript
  function bubbleSort(arr) {
    const n = arr.length;
    for (let i = 0; i < n - 1; i++) {
      for (let j = 0; j < n - i - 1; j++) {
        if (arr[j] > arr[j + 1]) {
          // Swap arr[j] and arr[j + 1]
          [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
        }
      }
    }
  }

  const unsortedArray = [64, 34, 25, 12, 22, 11, 90];
  bubbleSort(unsortedArray);

  console.log("Sorted Array:", unsortedArray);
  ```
