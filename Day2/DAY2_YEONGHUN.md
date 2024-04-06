# 두 수의 나눗셈

## 문제설명

<br>

> 📌 정수 `num1`과 `num2`가 매개변수로 주어질 때, `num1`을 `num2`로 나눈 값에 1,000을 곱한 후 정수 부분을 return 하도록 soltuion 함수를 완성해주세요.

<br>

---

## 제한사항
> * - 0 < `num1` ≤ 100
> * - 0 < `num2` ≤ 100

<br>

---

## 입출력 예



| num1 | num2 | result |
| ---- | ---- | ------ |
| 3    | 2    | 1500   |
| 7    | 3    | 2333   |
| 1    | 16   | 62     |

<br>

---

## Solution.java
```java
class Solution {
    public int solution(int num1, int num2) {
        return (int)(((double)num1 / num2) * 1000);
    }
}
```

---
* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120806)

<br>

---
# 배열 두 배 만들기

## 문제설명

<br>

> 📌 정수 배열 `numbers`가 매개변수로 주어집니다. `numbers`의 각 원소에 두배한 원소를 가진 배열을 return하도록 solution 함수를 완성해주세요.

<br>

---

## 제한사항
> * -10,000 ≤ `numbers`의 원소 ≤ 10,000
> - 1 ≤ `numbers`의 길이 ≤ 1,000

<br>

---

## 입출력 예

| numbers                   | result                     |
| ------------------------- | -------------------------- |
| [1,2,3,4,5]               | [2,4,6,8,10]               |
| [1, 2, 100, -99, 1, 2, 3] | [2, 4, 200, -198, 2, 4, 6] |
<br>

---

## 입출력 예 설명
>입출력 예 #1
>
>- [1, 2, 3, 4, 5]의 각 원소에 두배를 한 배열 [2, 4, 6, 8, 10]을 return합니다.
>
입출력 예 #2
>
>- [1, 2, 100, -99, 1, 2, 3]의 각 원소에 두배를 한 배열 [2, 4, 200, -198, 2, 4, 6]을 return합니다.

<br>

---

## Solution.java
```java
import java.util.stream.*;
class Solution {
    public int[] solution(int[] numbers) {
        return IntStream.of(numbers).map(a->a*2).toArray();
    }
}
```


<hr>

* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120809)

<br>

---
# 분수의 덧셈

## 문제설명

<br>

> 📌 첫 번째 분수의 분자와 분모를 뜻하는 `numer1`, `denom1`, 두 번째 분수의 분자와 분모를 뜻하는 `numer2`, `denom2`가 매개변수로 주어집니다. 두 분수를 더한 값을 기약 분수로 나타냈을 때 분자와 분모를 순서대로 담은 배열을 return 하도록 solution 함수를 완성해보세요.

<br>

---

## 제한사항
> * - 0 <`numer1`, `denom1`, `numer2`, `denom2` < 1,000

<br>

---

## 입출력 예

| numer1 | denom1 | numer2 | denom2 | result |
| ------ | ------ | ------ | ------ | ------ |
| 1      | 2      | 3      | 4      | [5,4]  |
| 9      | 2      | 1      | 3      | [29,6] |

<br>

---

## 입출력 예 설명
>입출력 예 #1
>
>- 1 / 2 + 3 / 4 = 5 / 4입니다. 따라서 [5, 4]를 return 합니다.
>
입출력 예 #2
>
>- 9 / 2 + 1 / 3 = 29 / 6입니다. 따라서 [29, 6]을 return 합니다.

<br>

---
## Solution.java
```java
class Solution {
    public int[] solution(int 분자1, int 분모1, int 분자2, int 분모2) {
        int 공통_분모 = 최소_공배수를_구한다(분모1, 분모2);
        int 분자의_합 = 분자1 * (공통_분모/분모1) + 분자2 * (공통_분모/분모2); 
        int 약분 = 최대_공약수를_구한다(분자의_합, 공통_분모); // -> 이거 빼먹어서 15분 더함 
        return new int[]{분자의_합/약분, 공통_분모/약분};
    }
    public int 최대_공약수를_구한다(int num1, int num2){
        return num2 == 0 ? num1 : 최대_공약수를_구한다(num2, num1 % num2);
        
    }
    public int 최소_공배수를_구한다(int num1, int num2){
        return (num1 * num2) / 최대_공약수를_구한다(num1, num2);
    }
}
```




<hr>
* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120808)

<br>

---
# 숫자 비교하기

## 문제설명

<br>

> 📌 정수 `num1`과 `num2`가 매개변수로 주어집니다. 두 수가 같으면 1 다르면 -1을 retrun하도록 solution 함수를 완성해주세요.

<br>

---

## 제한사항
> * - 0 ≤ `num1` ≤ 10,000
> * - 0 ≤ `num2` ≤ 10,000

<br>

---

## 입출력 예

| num1 | num2 | result |
| ---- | ---- | ------ |
| 2    | 3    | -1     |
| 11   | 11   | 1      |
| 7    | 99   | -1     |
<br>

---

## 입출력 예 설명
> 입출력 예 설명 #1
>
> - `num1`이 2이고 `num2`가 3이므로 다릅니다. 따라서 -1을 return합니다.
> 
입출력 예 설명 #2
> 
> - `num1`이 11이고 `num2`가 11이므로 같습니다. 따라서 1을 return합니다.
> 
입출력 예 설명 #3
> 
> - `num1`이 7이고 `num2`가 99이므로 다릅니다. 따라서 -1을 return합니다.

---

## Solution.java
```java
class Solution {
    public int solution(int num1, int num2) {
        return (num1 == num2) ? 1 : -1;
    }
}
```

 
<br>
<hr>

* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120807)