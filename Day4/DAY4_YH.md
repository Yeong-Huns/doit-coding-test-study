# 배열의 평균값

## 문제설명

<br>

> 📌 정수 배열 `numbers`가 매개변수로 주어집니다. `numbers`의 원소의 평균값을 return하도록 solution 함수를 완성해주세요.

<br>

---

## 제한사항

> - 0 ≤ `numbers`의 원소 ≤ 1,000
> - 1 ≤ `numbers`의 길이 ≤ 100
> - 정답의 소수 부분이 .0 또는 .5인 경우만 입력으로 주어집니다.

<br>

---

## 입출력 예

| numbers                                      | result |
| -------------------------------------------- | ------ |
| [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]              | 5.5    |
| [89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99] | 94.0   |
<br>

---

## 입출력 예 설명

> 입출력 예 #1
> - `numbers`의 원소들의 평균 값은 5.5입니다.

> 입출력 예 # 2
> - `numbers`의 원소들의 평균 값은 94.0입니다.

<br>

---
## Solution.java

```java
class Solution{
	public double solution(int[] numbers) {  
     return Arrays.stream(numbers)  
             .mapToDouble(i -> i)  
             .average()  
             .getAsDouble();  
	}
}
```
* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120817)

<br>

<hr>

# 피자 나눠 먹기 (1)

## 문제설명

<br>

> 📌 머쓱이네 피자가게는 피자를 일곱 조각으로 잘라 줍니다. 피자를 나눠먹을 사람의 수 `n`이 주어질 때, 모든 사람이 피자를 한 조각 이상 먹기 위해 필요한 피자의 수를 return 하는 solution 함수를 완성해보세요.

<br>

---

## 제한사항

> - 1 ≤ `n` ≤ 100


<br>

---

## 입출력 예

|n|result|
|---|---|
|7|1|
|1|1|
|15|3|

<br>

---

## 입출력 예 설명

> 입출력 예 #1
> - 7명이 최소 한 조각씩 먹기 위해서 최소 1판이 필요합니다.

> 입출력 예 # 2
> - 1명은 최소 한 조각을 먹기 위해 1판이 필요합니다.

> 입출력 예 # 2
> - 15명이 최소 한 조각씩 먹기 위해서 최소 3판이 필요합니다.

<br>

---
## Solution.java

```java
class Solution {
    public int solution(int n) {
       return n % 7 == 0 ?  n / 7 : n / 7 + 1;
    }
}
```
* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120814)

<br>

<hr>

# 피자 나눠 먹기 (2)

## 문제설명

<br>

> 📌 머쓱이네 피자가게는 피자를 여섯 조각으로 잘라 줍니다. 피자를 나눠먹을 사람의 수 `n`이 매개변수로 주어질 때, `n`명이 주문한 피자를 남기지 않고 모두 같은 수의 피자 조각을 먹어야 한다면 최소 몇 판을 시켜야 하는지를 return 하도록 solution 함수를 완성해보세요.

<br>

---

## 제한사항

> 1 ≤ `n` ≤ 100


<br>

---

## 입출력 예

| n   | result |
| --- | ------ |
| 6   | 1      |
| 10  | 5      |
| 4   | 2      |
<br>

---

## 입출력 예 설명

> 입출력 예 #1
> - 6명이 모두 같은 양을 먹기 위해 한 판을 시켜야 피자가 6조각으로 모두 한 조각씩 먹을 수 있습니다.

> 입출력 예 # 2
> - 10명이 모두 같은 양을 먹기 위해 최소 5판을 시켜야 피자가 30조각으로 모두 세 조각씩 먹을 수 있습니다.

> 입출력 예 # 2
> - 4명이 모두 같은 양을 먹기 위해 최소 2판을 시키면 피자가 12조각으로 모두 세 조각씩 먹을 수 있습니다.

<br>

---
## Solution.java

```java
import java.util.*;
class Solution{
    private final int 피자_조각;

	public Solution(){
		this.피자_조각 = 6;
	}
    
	public int solution(int 인원_수) {
        return 최소_공배수를_구한다(인원_수, 피자_조각) / 피자_조각;    
    }
    
    private int 최대_공약수를_구한다(int a, int b){
	    return (b == 0) ? a : 최대_공약수를_구한다(b, a % b);
    }
    
    private int 최소_공배수를_구한다(int a, int b){
	    return (a * b) / 최대_공약수를_구한다(a, b);
    }
}
```
* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120815?language=java)

<br>

---
# 피자 나눠 먹기 (3)

## 문제설명

<br>

> 📌 머쓱이네 피자가게는 피자를 두 조각에서 열 조각까지 원하는 조각 수로 잘라줍니다. 피자 조각 수 `slice`와 피자를 먹는 사람의 수 `n`이 매개변수로 주어질 때, `n`명의 사람이 최소 한 조각 이상 피자를 먹으려면 최소 몇 판의 피자를 시켜야 하는지를 return 하도록 solution 함수를 완성해보세요.

<br>

---

## 제한사항

> - 2 ≤ `slice` ≤ 10
> - 1 ≤ `n` ≤ 100

<br>

---

## 입출력 예

| slice | n   | result |
| ----- | --- | ------ |
| 7     | 10  | 2      |
| 4     | 12  | 3      |
<br>

---

## 입출력 예 설명

> 입출력 예 #1
>- 10명이 7조각으로 자른 피자를 한 조각 이상씩 먹으려면 최소 2판을 시켜야 합니다.

> 입출력 예 # 2
> - 12명이 4조각으로 자른 피자를 한 조각 이상씩 먹으려면 최소 3판을 시켜야 합니다.

<br>

---
## Solution.java

```java
class Solution {
    public int solution(int slice, int n) {
        return n % slice == 0 ? n / slice : n / slice + 1;
    }
}
```
* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120816)