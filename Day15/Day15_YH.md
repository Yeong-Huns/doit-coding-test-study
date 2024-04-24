# 코딩테스트 연습 - 약수 구하기 | 프로그래머스 스쿨

###### 문제 설명

정수 `n`이 매개변수로 주어질 때, `n`의 약수를 오름차순으로 담은 배열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `n` ≤ 10,000

---

##### 입출력 예

| n  | result                       |
| -- | ---------------------------- |
| 24 | \[1, 2, 3, 4, 6, 8, 12, 24\] |
| 29 | \[1, 29\]                    |

---

##### 입출력 예 설명

입출력 예 #1

* 24의 약수를 오름차순으로 담은 배열 \[1, 2, 3, 4, 6, 8, 12, 24\]를 return합니다.

입출력 예 #2

* 29의 약수를 오름차순으로 담은 배열 \[1, 29\]를 return합니다.

---
## Solution.java

```java
import java.util.stream.*;
class Solution {
    public int[] solution(int n) {
        return IntStream.rangeClosed(1,n)
            .filter(i->n%i==0)
            .toArray();
    }
}```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120897?language=java)

---

# 코딩테스트 연습 - 영어가 싫어요 | 프로그래머스 스쿨

###### 문제 설명

영어가 싫은 머쓱이는 영어로 표기되어있는 숫자를 수로 바꾸려고 합니다. 문자열 `numbers`가 매개변수로 주어질 때, `numbers`를 정수로 바꿔 return 하도록 solution 함수를 완성해 주세요.

---

##### 제한사항

* `numbers`는 소문자로만 구성되어 있습니다.
* `numbers`는 "zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine" 들이 공백 없이 조합되어 있습니다.
* 1 ≤ `numbers`의 길이 ≤ 50
* "zero"는 `numbers`의 맨 앞에 올 수 없습니다.

---

##### 입출력 예

| numbers                                | result    |
| -------------------------------------- | --------- |
| "onetwothreefourfivesixseveneightnine" | 123456789 |
| "onefourzerosixseven"                  | 14067     |

---

##### 입출력 예 설명

입출력 예 #1

* "onetwothreefourfivesixseveneightnine"를 숫자로 바꾼 123456789를 return합니다.

입출력 예 #1

* "onefourzerosixseven"를 숫자로 바꾼 14067를 return합니다.

---
## Solution.java

```java
class Solution {
    public long solution(String numbers) {
        numbers = numbers.toUpperCase();
        
        for(Number number : Number.values())
        numbers = numbers.replaceAll(number.toString(), number.getNumber());
        
        return Long.parseLong(numbers);
    }
    
    public enum Number {
        ZERO("0"), 
        ONE("1"), 
        TWO("2"), 
        THREE("3"), 
        FOUR("4"), 
        FIVE("5"), 
        SIX("6"), 
        SEVEN("7"), 
        EIGHT("8"), 
        NINE("9");
        private String number;
        private Number(String num){
            number = num;
        }

        public String getNumber() {
            return number;
        }
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120894)

---
# 코딩테스트 연습 - 인덱스 바꾸기 | 프로그래머스 스쿨

###### 문제 설명

문자열 `my_string`과 정수 `num1`, `num2`가 매개변수로 주어질 때, `my_string`에서 인덱스 `num1`과 인덱스 `num2`에 해당하는 문자를 바꾼 문자열을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 1 < `my_string`의 길이 < 100
* 0 ≤ `num1`, `num2` < `my_string`의 길이
* `my_string`은 소문자로 이루어져 있습니다.
* `num1` ≠ `num2`

---

##### 입출력 예

| my\_string   | num1 | num2 | result       |
| ------------ | ---- | ---- | ------------ |
| "hello"      | 1    | 2    | "hlelo"      |
| "I love you" | 3    | 6    | "I l veoyou" |

---

##### 입출력 예 설명

입출력 예 #1

* "hello"의 1번째 인덱스인 "e"와 2번째 인덱스인 "l"을 바꾸면 "hlelo"입니다.

입출력 예 #2

* "I love you"의 3번째 인덱스 "o"와 " "(공백)을 바꾸면 "I l veoyou"입니다.

---
## Solution.java

```java
class Solution {
    public String solution(String my_string, int num1, int num2) {
        String rs = "";
        for(int i = 0; i < my_string.length(); i++){
            if(i == num1||i == num2)
            rs += i == num1 ? my_string.charAt(num2) : 
            my_string.charAt(num1);
            else rs += my_string.charAt(i);
        }
        return rs;
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120895?language=java)

---
# 코딩테스트 연습 - 한 번만 등장한 문자 | 프로그래머스 스쿨

###### 문제 설명

문자열 `s`가 매개변수로 주어집니다. `s`에서 한 번만 등장하는 문자를 사전 순으로 정렬한 문자열을 return 하도록 solution 함수를 완성해보세요. 한 번만 등장하는 문자가 없을 경우 빈 문자열을 return 합니다.

---

##### 제한사항

* 0 < `s`의 길이 < 1,000
* `s`는 소문자로만 이루어져 있습니다.

---

##### 입출력 예

| s           | result |
| ----------- | ------ |
| "abcabcadc" | "d"    |
| "abdc"      | "abcd" |
| "hello"     | "eho"  |

---

##### 입출력 예 설명

입출력 예 #1

* "abcabcadc"에서 하나만 등장하는 문자는 "d"입니다.

입출력 예 #2

* "abdc"에서 모든 문자가 한 번씩 등장하므로 사전 순으로 정렬한 "abcd"를 return 합니다.

입출력 예 #3

* "hello"에서 한 번씩 등장한 문자는 "heo"이고 이를 사전 순으로 정렬한 "eho"를 return 합니다.

---
## Solution.java

```java
import java.util.*;
class Solution {
    public String solution(String s) {
        String rs = "";
        for(String i : s.split("")){
            int count = -1;
            for(String j : s.split("")){
                if(i.equals(j))count++;
                if(count >= 1)break;
            }
            rs = count == 0 ? rs+=i : rs;
        }
        char[] n1 = rs.toCharArray();
        Arrays.sort(n1); 
        String nn = new String(n1);
        return nn;
    }
}

////////////////// 다른 풀이 ////////////////////////

import java.util.*;
import java.util.stream.*;
class Solution {
    public String solution(String s) {
        return Arrays.stream(s.split(""))
            .collect(Collectors.groupingBy(i->i))
            .entrySet()
            .stream()
            .filter(e->e.getValue().size()<2)
            .map(엔트리->엔트리.getKey()) // == Map.Entry::getKey
            .sorted()
            .collect(Collectors.joining(""));
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120896?language=java)