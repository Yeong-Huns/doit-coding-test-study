# 코딩테스트 연습 - 가장 큰 수 찾기 | 프로그래머스 스쿨


###### 문제 설명

정수 배열 `array`가 매개변수로 주어질 때, 가장 큰 수와 그 수의 인덱스를 담은 배열을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 1 ≤ `array의` 길이 ≤ 100
* 0 ≤ `array` 원소 ≤ 1,000
* `array`에 중복된 숫자는 없습니다.

---

##### 입출력 예

| array            | result    |
| ---------------- | --------- |
| \[1, 8, 3\]      | \[8, 1\]  |
| \[9, 10, 11, 8\] | \[11, 2\] |

---

##### 입출력 예 설명

입출력 예 #1

* 1, 8, 3 중 가장 큰 수는 8이고 인덱스 1에 있습니다.

입출력 예 #2

* 9, 10, 11, 8 중 가장 큰 수는 11이고 인덱스 2에 있습니다.

---
## Solution.java

```java
import java.util.*;
import java.util.stream.*;
class Solution {
    public int[] solution(int[] array) {
        List<Integer> list =  Arrays.stream(array).boxed().collect(Collectors.toList());
        int max = Arrays.stream(array).max().getAsInt();
        return new int[]{max, list.indexOf(max)};
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120899)

---
# 코딩테스트 연습 - 문자열 계산하기 | 프로그래머스 스쿨


###### 문제 설명

`my_string`은 "3 + 5"처럼 문자열로 된 수식입니다. 문자열 `my_string`이 매개변수로 주어질 때, 수식을 계산한 값을 return 하는 solution 함수를 완성해주세요.

---

##### 제한사항

* 연산자는 +, -만 존재합니다.
* 문자열의 시작과 끝에는 공백이 없습니다.
* 0으로 시작하는 숫자는 주어지지 않습니다.
* 잘못된 수식은 주어지지 않습니다.
* 5 ≤ `my_string`의 길이 ≤ 100
* `my_string`을 계산한 결과값은 1 이상 100,000 이하입니다.  
   * `my_string`의 중간 계산 값은 -100,000 이상 100,000 이하입니다.  
   * 계산에 사용하는 숫자는 1 이상 20,000 이하인 자연수입니다.  
   * `my_string`에는 연산자가 적어도 하나 포함되어 있습니다.
* return type 은 정수형입니다.
* `my_string`의 숫자와 연산자는 공백 하나로 구분되어 있습니다.

---

##### 입출력 예

| my\_string | result |
| ---------- | ------ |
| "3 + 4"    | 7      |

---

##### 입출력 예 설명

입출력 예 #1

* 3 + 4 = 7을 return 합니다.
---
## Solution.java

```java
import java.util.*;
class Solution {
    public int solution(String 문자열) {
        int 숫자 = 0;
        String[] 배열 = 문자열.split(" ");
        숫자 += Integer.parseInt(배열[0]);
        for(int 인덱스 = 1; 인덱스 < 배열.length - 1; 인덱스++){
            if(배열[인덱스].equals("+")) 숫자+=Integer.parseInt(배열[인덱스+1]);
            if(배열[인덱스].equals("-")) 숫자-=Integer.parseInt(배열[인덱스+1]);
        }
        return 숫자;
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120902)

---
# 코딩테스트 연습 - 배열의 유사도 | 프로그래머스 스쿨


###### 문제 설명

두 배열이 얼마나 유사한지 확인해보려고 합니다. 문자열 배열 `s1`과 `s2`가 주어질 때 같은 원소의 개수를 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `s1`, `s2`의 길이 ≤ 100
* 1 ≤ `s1`, `s2`의 원소의 길이 ≤ 10
* `s1`과 `s2`의 원소는 알파벳 소문자로만 이루어져 있습니다
* `s1`과 `s2`는 각각 중복된 원소를 갖지 않습니다.

---

##### 입출력 예

| s1                | s2                            | result |
| ----------------- | ----------------------------- | ------ |
| \["a", "b", "c"\] | \["com", "b", "d", "p", "c"\] | 2      |
| \["n", "omg"\]    | \["m", "dot"\]                | 0      |

---

##### 입출력 예 설명

입출력 예 #1

* "b"와 "c"가 같으므로 2를 return합니다.

입출력 예 #2

* 같은 원소가 없으므로 0을 return합니다.

---
## Solution.java

```java
import java.util.*;
class Solution {
    public int solution(String[] s1, String[] s2) {
    Set<String> set = new HashSet<>(Arrays.asList(s1));
    return (int)Arrays.stream(s2).filter(n -> set.contains(n)).count();
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120903)

___
# 코딩테스트 연습 - 편지 | 프로그래머스 스쿨



###### 문제 설명

머쓱이는 할머니께 생신 축하 편지를 쓰려고 합니다. 할머니가 보시기 편하도록 글자 한 자 한 자를 가로 2cm 크기로 적으려고 하며, 편지를 가로로만 적을 때, 축하 문구 `message`를 적기 위해 필요한 편지지의 최소 가로길이를 return 하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 공백도 하나의 문자로 취급합니다.
* 1 ≤ message의 길이 ≤ 50
* 편지지의 여백은 생각하지 않습니다.
* `message`는 영문 알파벳 대소문자, ‘!’, ‘\~’ 또는 공백으로만 이루어져 있습니다.

---

##### 입출력 예

| message           | result |
| ----------------- | ------ |
| "happy birthday!" | 30     |
| "I love you\~"    | 22     |

---

##### 입출력 예 설명

입출력 예 #1

* `message`의 글자 수가 15개로 최소 가로 30cm의 편지지가 필요합니다.

입출력 예 #2

* `message`의 글자 수가 11개로 최소 가로 22cm의 편지지가 필요합니다.
---
## Solution.java

```java
function solution(message) {
    var answer = 0;
    answer = message.length * 2;
    return answer;
}```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120898)