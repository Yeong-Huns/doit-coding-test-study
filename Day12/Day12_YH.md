# 코딩테스트 연습 - 모음 제거 | 프로그래머스 스쿨](

###### 문제 설명

영어에선 a, e, i, o, u 다섯 가지 알파벳을 모음으로 분류합니다. 문자열 `my_string`이 매개변수로 주어질 때 모음을 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* `my_string`은 소문자와 공백으로 이루어져 있습니다.
* 1 ≤ `my_string`의 길이 ≤ 1,000

---

##### 입출력 예

| my\_string         | result      |
| ------------------ | ----------- |
| "bus"              | "bs"        |
| "nice to meet you" | "nc t mt y" |

---

##### 입출력 예 설명

입출력 예 #1

* "bus"에서 모음 u를 제거한 "bs"를 return합니다.

입출력 예 #1

* "nice to meet you"에서 모음 i, o, e, u를 모두 제거한 "nc t mt y"를 return합니다.


---
## Solution.java

```java
class Solution {
    public String solution(String my_string) {
        return my_string.replaceAll("[aeiou]", "");
    }
}
```

---

[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120849)

---
# 코딩테스트 연습 - 문자열 정렬하기 (1) | 프로그래머스 스쿨

###### 문제 설명

문자열 `my_string`이 매개변수로 주어질 때, `my_string` 안에 있는 숫자만 골라 오름차순 정렬한 리스트를 return 하도록 solution 함수를 작성해보세요.

---

##### 제한사항

* 1 ≤ `my_string`의 길이 ≤ 100
* `my_string`에는 숫자가 한 개 이상 포함되어 있습니다.
* `my_string`은 영어 소문자 또는 0부터 9까지의 숫자로 이루어져 있습니다. - - -

##### 입출력 예

| my\_string  | result            |
| ----------- | ----------------- |
| "hi12392"   | \[1, 2, 2, 3, 9\] |
| "p2o4i8gj2" | \[2, 2, 4, 8\]    |
| "abcde0"    | \[0\]             |

---

##### 입출력 예 설명

입출력 예 #1

* "hi12392"에 있는 숫자 1, 2, 3, 9, 2를 오름차순 정렬한 \[1, 2, 2, 3, 9\]를 return 합니다.

입출력 예 #2

* "p2o4i8gj2"에 있는 숫자 2, 4, 8, 2를 오름차순 정렬한 \[2, 2, 4, 8\]을 return 합니다.

입출력 예 #3

* "abcde0"에 있는 숫자 0을 오름차순 정렬한 \[0\]을 return 합니다.


---
## Solution.java

```java
class Solution {
    public int[] solution(String my_string) {
        return my_string.chars()
            .filter(Character::isDigit)
            .map(Character::getNumericValue)
            .sorted()
            .toArray();
    }
}```

---

[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120850)

---
# 코딩테스트 연습 - 소인수분해 | 프로그래머스 스쿨


###### 문제 설명

소인수분해란 어떤 수를 소수들의 곱으로 표현하는 것입니다. 예를 들어 12를 소인수 분해하면 2 \* 2 \* 3 으로 나타낼 수 있습니다. 따라서 12의 소인수는 2와 3입니다. 자연수 `n`이 매개변수로 주어질 때 `n`의 소인수를 오름차순으로 담은 배열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 2 ≤ `n` ≤ 10,000

---

##### 입출력 예

| n   | result         |
| --- | -------------- |
| 12  | \[2, 3\]       |
| 17  | \[17\]         |
| 420 | \[2, 3, 5, 7\] |

---

##### 입출력 예 설명

입출력 예 #1

* 12를 소인수분해하면 2 \* 2 \* 3 입니다. 따라서 \[2, 3\]을 return합니다.

입출력 예 #2

* 17은 소수입니다. 따라서 \[17\]을 return 해야 합니다.

입출력 예 #3

* 420을 소인수분해하면 2 \* 2 \* 3 \* 5 \* 7 입니다. 따라서 \[2, 3, 5, 7\]을 return합니다.


---
## Solution.java

```java
import java.util.*;
class Solution {
    private List<Integer> 소인수_목록 = new ArrayList<>();
    public int[] solution(int 매개_변수) {
        for(int 소수_후보 = 2; 소수_후보 <= 매개_변수; 소수_후보++){
            if(매개_변수%소수_후보==0) {
                소인수_목록.add(소수_후보);
                while(매개_변수%소수_후보==0)매개_변수/=소수_후보;
            }
        }
        return 소인수_목록.stream().distinct().mapToInt(i -> i).toArray();
    }
}
```

---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120852)

---
# 코딩테스트 연습 - 숨어있는 숫자의 덧셈 (1) | 프로그래머스 스쿨


###### 문제 설명

문자열 `my_string`이 매개변수로 주어집니다. `my_string`안의 모든 자연수들의 합을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `my_string`의 길이 ≤ 1,000
* `my_string`은 소문자, 대문자 그리고 한자리 자연수로만 구성되어있습니다.

---

##### 입출력 예

| my\_string      | result |
| --------------- | ------ |
| "aAb1B2cC34oOp" | 10     |
| "1a2b3c4d123"   | 16     |

---

##### 입출력 예 설명

입출력 예 #1

* "aAb1B2cC34oOp"안의 한자리 자연수는 1, 2, 3, 4 입니다. 따라서 1 + 2 + 3 + 4 = 10 을 return합니다.

입출력 예 #2

* "1a2b3c4d123Z"안의 한자리 자연수는 1, 2, 3, 4, 1, 2, 3 입니다. 따라서 1 + 2 + 3 + 4 + 1 + 2 + 3 = 16 을 return합니다.

---

##### 유의사항

* 연속된 숫자도 각각 한 자리 숫자로 취급합니다.


---
## Solution.java

```java
class Solution {
    public int solution(String my_string) {
        return my_string.chars()
            .filter(Character::isDigit)
            .map(Character::getNumericValue)
            .sum();
    }
}
```

---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120851)

