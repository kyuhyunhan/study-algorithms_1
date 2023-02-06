실생활에서 거의 쓰일 일이 전무한 비효율적인 bubble sort에 비해   더 일반적이고 자주 쓰이는 알고리즘

### 시간복잡도

bubble sort보다 효율이 좋긴하지만 여전히 O(n^2)이다. 더 작은 계수(coefficient)가 있을뿐

다뤄야하는 데이터가 average case일때는 그렇게 좋은 방법이라고 볼 수 없다.

그러나 다룰 데이터가 “**거의 정렬되어 있는(nearly-sorted)**” 리스트일 때, insertion sort는 click sort나 merge sort에 비해 아주 좋은 방법이 될 수 있다.

bubble sort와 동일하게 공간복잡도는 상수, stable한 정렬방법이라고 할 수 있다.

### 구현
```
function insertionSort(nums) {
  for (let i = 1; i < nums.length; i++) {
    let numberToInsert = nums[i]; // the numberToInsert number we're looking to insert
    let j; // the inner counter

    // loop from the right to the left
    for (j = i - 1; nums[j] > numberToInsert && j >= 0; j--) {
      // move numbers to the right until we find where to insert
      nums[j + 1] = nums[j];
    }

    // ***do the insertion***
    nums[j + 1] = numberToInsert;
  }
  return nums;
}
```
