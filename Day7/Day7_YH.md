# 코딩테스트 연습 - 각도기 | 프로그래머스 스쿨


###### 문제 설명

각에서 0도 초과 90도 미만은 예각, 90도는 직각, 90도 초과 180도 미만은 둔각 180도는 평각으로 분류합니다. 각 `angle`이 매개변수로 주어질 때 예각일 때 1, 직각일 때 2, 둔각일 때 3, 평각일 때 4를 return하도록 solution 함수를 완성해주세요.

* 예각 : 0 < `angle` < 90
* 직각 : `angle` \= 90
* 둔각 : 90 < `angle` < 180
* 평각 : `angle` \= 180

---

##### 제한사항

* 0 < `angle` ≤ 180
* `angle`은 정수입니다.

---

##### 입출력 예

| angle | result |
| ----- | ------ |
| 70    | 1      |
| 91    | 3      |
| 180   | 4      |

---

##### 입출력 예 설명

입출력 예 #1

* `angle`이 70이므로 예각입니다. 따라서 1을 return합니다.

입출력 예 #2

* `angle`이 91이므로 둔각입니다. 따라서 3을 return합니다.

입출력 예 #2

* `angle`이 180이므로 평각입니다. 따라서 4를 return합니다.



---
## Solution.java

```java
class Solution {
    public int solution(int angle) {
       return angle < 90 ?
        1 : angle == 90 ?
         2 : 90 < angle && angle < 180 ?
          3 : 4;
    }
}
```

---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120829)

---
# 코딩테스트 연습 - 양꼬치 | 프로그래머스 스쿨
###### 문제 설명

머쓱이네 양꼬치 가게는 10인분을 먹으면 음료수 하나를 서비스로 줍니다. 양꼬치는 1인분에 12,000원, 음료수는 2,000원입니다. 정수 `n`과 `k`가 매개변수로 주어졌을 때, 양꼬치 `n`인분과 음료수 `k`개를 먹었다면 총얼마를 지불해야 하는지 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 0 < `n` < 1,000
* n / 10 ≤ `k` < 1,000
* 서비스로 받은 음료수는 모두 마십니다.

---

##### 입출력 예

| n  | k | result  |
| -- | - | ------- |
| 10 | 3 | 124,000 |
| 64 | 6 | 768,000 |

---

##### 입출력 예 설명

입출력 예 #1

* 10인분을 시켜 서비스로 음료수를 하나 받아 총 10 \* 12000 + 3 \* 2000 - 1 \* 2000 = 124,000원입니다.

입출력 예 #2

* 64인분을 시켜 서비스로 음료수를 6개 받아 총 64 \* 12000 + 6 \* 2000 - 6 \* 2000 =768,000원입니다.

---
## Solution.java

```java
class Solution {
    public int solution(int n, int k) {
        return 12000 * n + 2000 * (k - (n / 10));
    }
}
```

---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120830)

---
# 코딩테스트 연습 - 짝수의 합 | 프로그래머스 스쿨


###### 문제 설명

정수 `n`이 주어질 때, `n`이하의 짝수를 모두 더한 값을 return 하도록 solution 함수를 작성해주세요.

---

##### 제한사항

0 < `n` ≤ 1000

---

##### 입출력 예

| n  | result |
| -- | ------ |
| 10 | 30     |
| 4  | 6      |

---

##### 입출력 예 설명

입출력 예 #1

* `n`이 10이므로 2 + 4 + 6 + 8 + 10 = 30을 return 합니다.

입출력 예 #2

* `n`이 4이므로 2 + 4 = 6을 return 합니다.

---
## Solution.java

```java
import java.util.*;
import java.util.stream.*;
class Solution {
    public int solution(int n) {
        return IntStream.rangeClosed(1, n).filter(i->i%2==0).sum();
    }
}
```

---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120831?language=java)

---
# 코딩테스트 연습 - 특정 문자 제거하기 | 프로그래머스 스쿨

###### 문제 설명

문자열 `my_string`과 문자 `letter`이 매개변수로 주어집니다. `my_string`에서 `letter`를 제거한 문자열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `my_string`의 길이 ≤ 100
* `letter`은 길이가 1인 영문자입니다.
* `my_string`과 `letter`은 알파벳 대소문자로 이루어져 있습니다.
* 대문자와 소문자를 구분합니다.

---

##### 입출력 예

| my\_string | letter | result  |
| ---------- | ------ | ------- |
| "abcdef"   | "f"    | "abcde" |
| "BCBdbe"   | "B"    | "Cdbe"  |

---

##### 입출력 예 설명

입출력 예 #1

* "abcdef" 에서 "f"를 제거한 "abcde"를 return합니다.

입출력 예 #2

* "BCBdbe" 에서 "B"를 모두 제거한 "Cdbe"를 return합니다.


---
## Solution.java

```java
class Solution {
    public String solution(String my_string, String letter) {
        return my_string.replaceAll(letter, "");
    }
}
```

---
[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120826?language=java)