# wiggle-sort

### Implementation :

```java
  public static void wiggleSort(int[] arr) {
      if(arr == null || arr.length <= 1)
        return;
	  	for(int i = 1; i < arr.length; i++) {
        if(i % 2 == 1) {
          if(arr[i] < arr[i-1]) 
            swap(arr,i, i-1);
        } else {
          if(arr[i] > arr[i-1]) 
            swap(arr, i, i-1);
        }
		  }
	}


	private static void swap(int[] arr, int i , int j) {
		int temp = arr[i];
		arr[i] = arr[j];
		arr[j] = temp;
	}
```
