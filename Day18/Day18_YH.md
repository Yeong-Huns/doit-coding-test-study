
# 코딩테스트 연습 - 문자열 정렬하기 (2) | 프로그래머스 스쿨


###### 문제 설명

영어 대소문자로 이루어진 문자열 `my_string`이 매개변수로 주어질 때, `my_string`을 모두 소문자로 바꾸고 알파벳 순서대로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 0 < `my_string` 길이 < 100

---

##### 입출력 예

| my\_string | result   |
| ---------- | -------- |
| "Bcad"     | "abcd"   |
| "heLLo"    | "ehllo"  |
| "Python"   | "hnopty" |

---

##### 입출력 예 설명

입출력 예 #1

* "Bcad"를 모두 소문자로 바꾸면 "bcad"이고 이를 알파벳 순으로 정렬하면 "abcd"입니다.

입출력 예 #2

* "heLLo"를 모두 소문자로 바꾸면 "hello"이고 이를 알파벳 순으로 정렬하면 "ehllo"입니다.

입출력 예 #3

* "Python"를 모두 소문자로 바꾸면 "python"이고 이를 알파벳 순으로 정렬하면 "hnopty"입니다.

---
## Solution.java

```java
import java.util.*;
import java.util.stream.*;
class Solution {
    public String solution(String my_string) {
         return Arrays.stream(my_string.toLowerCase().split(""))
            .sorted()
            .collect(Collectors.joining());
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120911)

---
# 코딩테스트 연습 - 문자열안에 문자열 | 프로그래머스 스쿨


###### 문제 설명

문자열 `str1`, `str2`가 매개변수로 주어집니다. `str1` 안에 `str2`가 있다면 1을 없다면 2를 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `str1`의 길이 ≤ 100
* 1 ≤ `str2`의 길이 ≤ 100
* 문자열은 알파벳 대문자, 소문자, 숫자로 구성되어 있습니다.

---

##### 입출력 예

| str1                     | str2   | result |
| ------------------------ | ------ | ------ |
| "ab6CDE443fgh22iJKlmn1o" | "6CD"  | 1      |
| "ppprrrogrammers"        | "pppp" | 2      |
| "AbcAbcA"                | "AAA"  | 2      |

---

##### 입출력 예 설명

입출력 예 #1

* "ab`6CD`E443fgh22iJKlmn1o" `str1`에 `str2`가 존재하므로 1을 return합니다.

입출력 예 #2

* "ppprrrogrammers" `str1`에 `str2`가 없으므로 2를 return합니다.

입출력 예 #3

* "AbcAbcA" `str1`에 `str2`가 없으므로 2를 return합니다.
---
## Solution.java

```java
class Solution {
    public int solution(String str1, String str2) {
        return str1.contains(str2) ? 1 : 2;
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120908)

---
# 코딩테스트 연습 - 세균 증식 | 프로그래머스 스쿨


###### 문제 설명

어떤 세균은 1시간에 두배만큼 증식한다고 합니다. 처음 세균의 마리수 `n`과 경과한 시간 `t`가 매개변수로 주어질 때 `t`시간 후 세균의 수를 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `n` ≤ 10
* 1 ≤ `t` ≤ 15

---

##### 입출력 예

| n | t  | result  |
| - | -- | ------- |
| 2 | 10 | 2048    |
| 7 | 15 | 229,376 |

---

##### 입출력 예 설명

입출력 예 #1

* 처음엔 2마리, 1시간 후엔 4마리, 2시간 후엔 8마리, ..., 10시간 후엔 2048마리가 됩니다. 따라서 2048을 return합니다.

입출력 예 #2

* 처음엔 7마리, 1시간 후엔 14마리, 2시간 후엔 28마리, ..., 15시간 후엔 229376마리가 됩니다. 따라서 229,376을 return합니다.
---
## Solution.java

```java
import java.util.*;
class Solution {
    public int solution(int n, int t) {
        //2-> 1: 2 , 2: 4  .. 10: 1024 
        //7-> 1: 2 , 2: 4
     return n * (int)Math.pow(2, t);
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120910)

---

# 코딩테스트 연습 - 제곱수 판별하기 | 프로그래머스 스쿨

###### 문제 설명

어떤 자연수를 제곱했을 때 나오는 정수를 제곱수라고 합니다. 정수 `n`이 매개변수로 주어질 때, `n`이 제곱수라면 1을 아니라면 2를 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `n` ≤ 1,000,000

---

##### 입출력 예

| n   | result |
| --- | ------ |
| 144 | 1      |
| 976 | 2      |

---

##### 입출력 예 설명

입출력 예 #1

* 144는 12의 제곱이므로 제곱수입니다. 따라서 1을 return합니다.

입출력 예 #2

* 976은 제곱수가 아닙니다. 따라서 2를 return합니다.
---
## Solution.java

```java
class Solution {
    public int solution(int n) {
        return (int)Math.sqrt(n) * (int)Math.sqrt(n) == n ? 1 : 2;
    }
}

//////더 나은 풀이 ㅠㅠ
class Solution {
	public int solution(int n) {
        return Math.sqrt(n) % 1 == 0 ? 1 : 2;
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120909)

