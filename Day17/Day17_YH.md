# 코딩테스트 연습 - 숫자 찾기 | 프로그래머스 스쿨


###### 문제 설명

정수 `num`과 `k`가 매개변수로 주어질 때, `num`을 이루는 숫자 중에 `k`가 있으면 `num`의 그 숫자가 있는 자리 수를 return하고 없으면 -1을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 0 < `num` < 1,000,000
* 0 ≤ `k` < 10
* `num`에 `k`가 여러 개 있으면 가장 처음 나타나는 자리를 return 합니다.

---

##### 입출력 예

| num    | k | result |
| ------ | - | ------ |
| 29183  | 1 | 3      |
| 232443 | 4 | 4      |
| 123456 | 7 | \-1    |

---

##### 입출력 예 설명

입출력 예 #1

* 29183에서 1은 3번째에 있습니다.

입출력 예 #2

* 232443에서 4는 4번째에 처음 등장합니다.

입출력 예 #3

* 123456에 7은 없으므로 -1을 return 합니다.


---
## Solution.java

```java
class Solution {
    public int solution(int num, int k) {       
        return (num+"").contains(k+"") ? 
        (num+"").indexOf(k+"")+1 : 
        (num+"").indexOf(k+"");
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120904)


# 코딩테스트 연습 - 자릿수 더하기 | 프로그래머스 스쿨


###### 문제 설명

정수 `n`이 매개변수로 주어질 때 `n`의 각 자리 숫자의 합을 return하도록 solution 함수를 완성해주세요

---

##### 제한사항

* 0 ≤ `n` ≤ 1,000,000

---

##### 입출력 예

| n      | result |
| ------ | ------ |
| 1234   | 10     |
| 930211 | 16     |

---

##### 입출력 예 설명

입출력 예 #1

* 1 + 2 + 3 + 4 = 10을 return합니다.

입출력 예 #2

* 9 + 3 + 0 + 2 + 1 + 1 = 16을 return합니다.


---
## Solution.java

```java
import java.util.*;
class Solution {
    public int solution(int n) {
        return Arrays.stream((n+"").split(""))
            .mapToInt(Integer::parseInt)
            .sum();
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120906)


# 코딩테스트 연습 - n의 배수 고르기 | 프로그래머스 스쿨

###### 문제 설명

정수 `n`과 정수 배열 `numlist`가 매개변수로 주어질 때, `numlist`에서 `n`의 배수가 아닌 수들을 제거한 배열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `n` ≤ 10,000
* 1 ≤ `numlist`의 크기 ≤ 100
* 1 ≤ `numlist`의 원소 ≤ 100,000

---

##### 입출력 예

| n  | numlist                          | result               |
| -- | -------------------------------- | -------------------- |
| 3  | \[4, 5, 6, 7, 8, 9, 10, 11, 12\] | \[6, 9, 12\]         |
| 5  | \[1, 9, 3, 10, 13, 5\]           | \[10, 5\]            |
| 12 | \[2, 100, 120, 600, 12, 12\]     | \[120, 600, 12, 12\] |

---

##### 입출력 예 설명

입출력 예 #1

* `numlist`에서 3의 배수만을 남긴 \[6, 9, 12\]를 return합니다.

입출력 예 #2

* `numlist`에서 5의 배수만을 남긴 \[10, 5\]를 return합니다.

입출력 예 #3

* `numlist`에서 12의 배수만을 남긴 \[120, 600, 12, 12\]를 return합니다.


---
## Solution.java

```java
import java.util.*;
class Solution {
    public int[] solution(int n, int[] numlist) {
    return Arrays.stream(numlist)
        .filter(i -> i % n == 0)
        .toArray();
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120905)


# 코딩테스트 연습 - OX퀴즈 | 프로그래머스 스쿨


###### 문제 설명

덧셈, 뺄셈 수식들이 'X \[연산자\] Y = Z' 형태로 들어있는 문자열 배열 `quiz`가 매개변수로 주어집니다. 수식이 옳다면 "O"를 틀리다면 "X"를 순서대로 담은 배열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 연산 기호와 숫자 사이는 항상 하나의 공백이 존재합니다. 단 음수를 표시하는 마이너스 기호와 숫자 사이에는 공백이 존재하지 않습니다.
* 1 ≤ `quiz`의 길이 ≤ 10
* X, Y, Z는 각각 0부터 9까지 숫자로 이루어진 정수를 의미하며, 각 숫자의 맨 앞에 마이너스 기호가 하나 있을 수 있고 이는 음수를 의미합니다.
* X, Y, Z는 0을 제외하고는 0으로 시작하지 않습니다.
* \-10,000 ≤ X, Y ≤ 10,000
* \-20,000 ≤ Z ≤ 20,000
* \[연산자\]는 + 와 - 중 하나입니다.

---

##### 입출력 예

| quiz                                                         | result                 |
| ------------------------------------------------------------ | ---------------------- |
| \["3 - 4 = -3", "5 + 6 = 11"\]                               | \["X", "O"\]           |
| \["19 - 6 = 13", "5 + 66 = 71", "5 - 15 = 63", "3 - 1 = 2"\] | \["O", "O", "X", "O"\] |

---

##### 입출력 예 설명

입출력 예 #1

* 3 - 4 = -3 은 틀린 수식이므로 "X", 5 + 6 = 11 은 옳은 수식이므로 "O" 입니다. 따라서 \["X", "O"\]를 return합니다.

입출력 예 #2

* 19 - 6 = 13 은 옳은 수식이므로 "O", 5 + 66 = 71 은 옳은 수식이므로 "O", 5 - 15 = 63 은 틀린 수식이므로 "X", 3 - 1 = 2는 옳은 수식이므로 "O" 따라서 \["O", "O", "X", "O"\]를 return합니다.

---
## Solution.java

```java
class Solution {
    public String[] solution(String[] quiz) {
        String[] rs = new String[quiz.length];
        for(int i = 0; i < quiz.length; i++){
            String[] temp = quiz[i].split(" ");
            int t = Integer.parseInt(temp[0]) 
            + Integer.parseInt(temp[2]) 
            * (temp[1].equals("+")?1:-1);             
            rs[i] = t ==Integer.parseInt(temp[4]) ? "O" : "X";            
            }
        return rs;
        }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120907)