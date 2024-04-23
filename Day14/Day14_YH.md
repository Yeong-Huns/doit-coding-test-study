# 코딩테스트 연습 - 369게임 | 프로그래머스 스쿨

###### 문제 설명

머쓱이는 친구들과 369게임을 하고 있습니다. 369게임은 1부터 숫자를 하나씩 대며 3, 6, 9가 들어가는 숫자는 숫자 대신 3, 6, 9의 개수만큼 박수를 치는 게임입니다. 머쓱이가 말해야하는 숫자 `order`가 매개변수로 주어질 때, 머쓱이가 쳐야할 박수 횟수를 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 1 ≤ `order` ≤ 1,000,000

---

##### 입출력 예

| order | result |
| ----- | ------ |
| 3     | 1      |
| 29423 | 2      |

---

##### 입출력 예 설명

입출력 예 #1

* 3은 3이 1개 있으므로 1을 출력합니다.

입출력 예 #2

* 29423은 3이 1개, 9가 1개 있으므로 2를 출력합니다.

---

※ 공지 - 2023년 03월 24일 테스트 케이스가 추가되었습니다. 기존에 제출한 코드가 통과하지 못할 수도 있습니다.

---
## Solution.java

```java
import java.util.*;
import java.util.stream.*;
class Solution {
    public int solution(int order) {
        return 
            Arrays.stream((order+"")
            .split(""))
            .filter(i->"369".contains(i))
            .collect(Collectors.joining(""))
            .length();
            //스트림이 쓰고 싶었어..
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120891)

---
# 코딩테스트 연습 - 가까운 수 | 프로그래머스 스쿨

###### 문제 설명

정수 배열 `array`와 정수 `n`이 매개변수로 주어질 때, `array`에 들어있는 정수 중 `n`과 가장 가까운 수를 return 하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `array`의 길이 ≤ 100
* 1 ≤ `array`의 원소 ≤ 100
* 1 ≤ `n` ≤ 100
* 가장 가까운 수가 여러 개일 경우 더 작은 수를 return 합니다.

---

##### 입출력 예

| array          | n  | result |
| -------------- | -- | ------ |
| \[3, 10, 28\]  | 20 | 28     |
| \[10, 11, 12\] | 13 | 12     |

---

##### 입출력 예 설명

입출력 예 #1

* 3, 10, 28 중 20과 가장 가까운 수는 28입니다.

입출력 예 #2

* 10, 11, 12 중 13과 가장 가까운 수는 12입니다.

※ 공지 - 2023년 3월 29일 테스트 케이스가 추가되었습니다. 기존에 제출한 코드가 통과하지 못할 수도 있습니다.

---
## Solution.java

```java
import java.util.*;
import java.util.stream.*;
class Solution {
    public int solution(int[] array, int n) {
        int min = 101;
        int rs = 101;
        for(int temp : array){
            if(Math.abs(temp - n) < min){
                min = Math.abs(temp - n);
                rs = temp;
            }
            if(Math.abs(temp - n) == min){
                rs = rs > temp ? temp : rs;
            }
        }    
        System.out.println(min);
        System.out.println(rs);
        return rs;
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120890)

---
# 코딩테스트 연습 - 대문자와 소문자 | 프로그래머스 스쿨


###### 문제 설명

문자열 `my_string`이 매개변수로 주어질 때, 대문자는 소문자로 소문자는 대문자로 변환한 문자열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `my_string`의 길이 ≤ 1,000
* `my_string`은 영어 대문자와 소문자로만 구성되어 있습니다.

---

##### 입출력 예

| my\_string   | result       |
| ------------ | ------------ |
| "cccCCC"     | "CCCccc"     |
| "abCdEfghIJ" | "ABcDeFGHij" |

---

##### 입출력 예 설명

입출력 예 #1

* 소문자는 대문자로 대문자는 소문자로 바꾼 "CCCccc"를 return합니다.

입출력 예 #2

* 소문자는 대문자로 대문자는 소문자로 바꾼 "ABcDeFGHij"를 return합니다.

---
## Solution.java

```java
import java.util.*;
import java.util.stream.*;
class Solution {
    public String solution(String my_string) {
    return Arrays.stream(my_string.split(""))
        .map(i->i.equals(i.toUpperCase()) ? i.toLowerCase() : i.toUpperCase())
        .collect(Collectors.joining());
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120893)

---
# 코딩테스트 연습 - 암호 해독 | 프로그래머스 스쿨




###### 문제 설명

군 전략가 머쓱이는 전쟁 중 적군이 다음과 같은 암호 체계를 사용한다는 것을 알아냈습니다.

* 암호화된 문자열 `cipher`를 주고받습니다.
* 그 문자열에서 `code`의 배수 번째 글자만 진짜 암호입니다.

문자열 `cipher`와 정수 `code`가 매개변수로 주어질 때 해독된 암호 문자열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `cipher`의 길이 ≤ 1,000
* 1 ≤ `code` ≤ `cipher`의 길이
* `cipher`는 소문자와 공백으로만 구성되어 있습니다.
* 공백도 하나의 문자로 취급합니다.

---

##### 입출력 예

| cipher                     | code | result     |
| -------------------------- | ---- | ---------- |
| "dfjardstddetckdaccccdegk" | 4    | "attack"   |
| "pfqallllabwaoclk"         | 2    | "fallback" |

---

##### 입출력 예 설명

입출력 예 #1

* "dfjardstddetckdaccccdegk" 의 4번째, 8번째, 12번째, 16번째, 20번째, 24번째 글자를 합친 "attack"을 return합니다.

입출력 예 #2

* "pfqallllabwaoclk" 의 2번째, 4번째, 6번째, 8번째, 10번째, 12번째, 14번째, 16번째 글자를 합친 "fallback"을 return합니다.

---
## Solution.java

```java
import java.util.stream.*;
import java.util.*;
class Solution {
    public String solution(String cipher, int code) {
        String str = "";
        for(int i = code-1; i < cipher.length(); i += code){
            str+=cipher.charAt(i);
        }
        return str;
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120892)