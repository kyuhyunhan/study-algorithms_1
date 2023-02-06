복잡한 문제를 동일한 모델의 더 작은 문제로 나누어 계산하는 방식

어떤 개념을 설명할 때, 그 개념 자신을 이용해 설명하는 것을 recursion이라고 한다. 당연히 "super useful"하지 않다. 최소한 코드는 보기 좋다.

recursion은 반드시 base case를 가지고 있다. base case가 없다면 stak overflow가 될 것이다.

### 피보나치
recursion이 사용되는 가장 유명한 예시
```
function fibonacci(n) {
  // base case
  if (n === 2 || n === 1) {
    return 1;
  } else if (n <= 0) {
    return 0;
  }

  // recursive calls
  return fibonacci(n - 1) + fibonacci(n - 2);
}
```
### 효율성
그렇게 많지 않은 연산을 수행하는 경우라면 recursion은 꽤 나쁘지 않은 방법일 수 있다.

그러나 반복되는 많은 연산을 수행해야 하는 경우라면, recursion은 지나치게 많은 컴퓨팅을 수행해야 한다.

위와 같은 코드는 `fibonacci(100)`만 해도 벌써 연산이 느려지는 것이 확 체감된다.

아래와 같은 코드는 recursion을 사용할 때보다는 조금 더 가독성이 떨어지겠지만 적어도 효율면에서는 훨씬 뛰어나다.

```
function fibonacci(n) {
  const sequence = [0, 1];
  for (let i = 2; i < n + 1; i++) {
    sequence.push(sequence[i - 2] + sequence[i - 1]);
  }
  return sequence[n];
}
```
