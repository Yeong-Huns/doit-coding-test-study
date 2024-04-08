# 코딩테스트 연습 - 나이 출력 | 프로그래머스 스쿨
###### 문제 설명

머쓱이는 선생님이 몇 년도에 태어났는지 궁금해졌습니다. 2022년 기준 선생님의 나이 `age`가 주어질 때, 선생님의 출생 연도를 return 하는 solution 함수를 완성해주세요

---

##### 제한사항

* 0 < age ≤ 120
* 나이는 태어난 연도에 1살이며 매년 1월 1일마다 1살씩 증가합니다.

---

##### 입출력 예

| age | result |
| --- | ------ |
| 40  | 1983   |
| 23  | 2000   |

---

##### 입출력 예 설명

입출력 예 #1

* 2022년 기준 40살이므로 1983년생입니다.

입출력 예 #2

* 2022년 기준 23살이므로 2000년생입니다.

---
* ## Solution.java

```java
class Solution {
    public int solution(int age) {
        return 2023 - age;
    }
}
```

※ 공지 - 2024년 3월 14일 문제 지문이 보다 명확하게 수정되었습니다.

---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120820)

---
# 코딩테스트 연습 - 배열 뒤집기 | 프로그래머스 스쿨

###### 문제 설명

정수가 들어 있는 배열 `num_list`가 매개변수로 주어집니다. `num_list`의 원소의 순서를 거꾸로 뒤집은 배열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `num_list`의 길이 ≤ 1,000
* 0 ≤ `num_list`의 원소 ≤ 1,000

---

##### 입출력 예

| num\_list               | result                  |
| ----------------------- | ----------------------- |
| \[1, 2, 3, 4, 5\]       | \[5, 4, 3, 2, 1\]       |
| \[1, 1, 1, 1, 1, 2\]    | \[2, 1, 1, 1, 1, 1\]    |
| \[1, 0, 1, 1, 1, 3, 5\] | \[5, 3, 1, 1, 1, 0, 1\] |

---

##### 입출력 예 설명

입출력 예 #1

* `num_list`가 \[1, 2, 3, 4, 5\]이므로 순서를 거꾸로 뒤집은 배열 \[5, 4, 3, 2, 1\]을 return합니다.

입출력 예 #2

* `num_list`가 \[1, 1, 1, 1, 1, 2\]이므로 순서를 거꾸로 뒤집은 배열 \[2, 1, 1, 1, 1, 1\]을 return합니다.

입출력 예 #3

* `num_list`가 \[1, 0, 1, 1, 1, 3, 5\]이므로 순서를 거꾸로 뒤집은 배열 \[5, 3, 1, 1, 1, 0, 1\]을 return합니다.

---
## Solution.java

```java
import java.util.*;
import java.util.stream.*;
class Solution {
    public int[] solution(int[] array) {
	return IntStream.rangeClosed(1, array.length)
    .map(i->array[array.length - i])
    .toArray();
    }
}
```


---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120821)

---
# 코딩테스트 연습 - 아이스 아메리카노 | 프로그래머스 스쿨
###### 문제 설명

머쓱이는 추운 날에도 아이스 아메리카노만 마십니다. 아이스 아메리카노는 한잔에 5,500원입니다. 머쓱이가 가지고 있는 돈 `money`가 매개변수로 주어질 때, 머쓱이가 최대로 마실 수 있는 아메리카노의 잔 수와 남는 돈을 순서대로 담은 배열을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 0 < `money` ≤ 1,000,000

---

##### 입출력 예

| money  | result      |
| ------ | ----------- |
| 5,500  | \[1, 0\]    |
| 15,000 | \[2, 4000\] |

---

##### 입출력 예 설명

입출력 예 #1

* 5,500원은 아이스 아메리카노 한 잔을 살 수 있고 잔돈은 0원입니다.

입출력 예 #2

* 15,000원은 아이스 아메리카노 두 잔을 살 수 있고 잔돈은 4,000원입니다.

---
## Solution.java

```java
class Solution {
    private final int coffee = 5500;
	    public int[] solution(int money) {
        return new int[]{money/coffee, money%coffee};
    }
}```

---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120819)

---
# 코딩테스트 연습 - 옷가게 할인 받기 | 프로그래머스 스쿨

###### 문제 설명

머쓱이네 옷가게는 10만 원 이상 사면 5%, 30만 원 이상 사면 10%, 50만 원 이상 사면 20%를 할인해줍니다.  
구매한 옷의 가격 `price`가 주어질 때, 지불해야 할 금액을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 10 ≤ `price` ≤ 1,000,000  
   * `price`는 10원 단위로(1의 자리가 0) 주어집니다.
* 소수점 이하를 버린 정수를 return합니다.

---

##### 입출력 예

| price   | result  |
| ------- | ------- |
| 150,000 | 142,500 |
| 580,000 | 464,000 |

---

##### 입출력 예 설명

입출력 예 #1

* 150,000원에서 5%를 할인한 142,500원을 return 합니다.

입출력 예 #2

* 580,000원에서 20%를 할인한 464,000원을 return 합니다.

---
## Solution.java

```java
class Solution {
	public int solution(int price) {
	return price >= 500000 ? (int)(price * 0.8) : price >= 300000 ?
	(int)(price * 0.9) : price >= 100000 ? (int)(price * 0.95) : price;
	}
}

```

[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120818)