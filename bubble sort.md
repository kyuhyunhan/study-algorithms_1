가장 큰 숫자가 bubble to the last spot 이라는 의미로 이해하면 bubble sort라는 의미가 이해가 된다.

### 시간복잡도

Best case는 O(n), Worst case는 O(n^2)

Average case는 O(n^2)

한번 inner loop을 돌 때마다 가장 뒤에서 loop을 돈 횟수만큼의 숫자는 정렬이 되었다고 볼 수 있다. 그렇기 때문에 언제나 전체 index - i 까지만 검사를 하고 swap을 하면 된다. 이것이 약간의 최적화를 가능하게 할 것이다.

### 공간복잡도

존재하는 배열 그 자체를 섞는 정렬이므로 공간복잡도는 상수이다. 이럴경우 이 정렬은 destructive 하다고 표현한다.

### stable sorting algorithm

두 개의 값이 같을 때 두 값의 순서가 보존되는 경우는 stable 한 정렬이라고 표현할 수 있는데, 이 bubble sort가 그러하다.

### 구현
```
function bubbleSort(nums) {
	let swapped = false;
	do {
		swapped = false;
		for (let i = 0; i < nums.length; i++) {
			if (nums[i] > nums[i+1]) {
				const temp = nums[i];
				nums[i] = nums[i+1];
				nums[i+1] = temp;
				swapped = true;
			}
		}
	} while(swapped)
}
```
