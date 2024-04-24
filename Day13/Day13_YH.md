# 코딩테스트 연습 - 배열 원소의 길이 | 프로그래머스 스쿨




###### 문제 설명

문자열 배열 `strlist`가 매개변수로 주어집니다. `strlist` 각 원소의 길이를 담은 배열을 retrun하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `strlist` 원소의 길이 ≤ 100
* `strlist`는 알파벳 소문자, 대문자, 특수문자로 구성되어 있습니다.

---

##### 입출력 예

| strlist                          | result         |
| -------------------------------- | -------------- |
| \["We", "are", "the", "world!"\] | \[2, 3, 3, 6\] |
| \["I", "Love", "Programmers."\]  | \[1, 4, 12\]   |

---

##### 입출력 예 설명

입출력 예 #1

* \["We", "are", "the", "world!"\]의 각 원소의 길이인 \[2, 3, 3, 6\]을 return합니다.

입출력 예 #2

* \["I", "Love", "Programmers."\]의 각 원소의 길이인 \[1, 4, 12\]을 return합니다.

---
## Solution.java

```java
class Solution {
    public int[] solution(String[] strlist) {
        int[] answer = new int[strlist.length];
        int index = 0;
        for(String i : strlist){
            answer[index] = i.length();
            index+=1;
        }
        return answer;
    }
}
```

---

* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120854)

---

# 코딩테스트 연습 - 삼각형의 완성조건 (1) | 프로그래머스 스쿨


###### 문제 설명

선분 세 개로 삼각형을 만들기 위해서는 다음과 같은 조건을 만족해야 합니다.

* 가장 긴 변의 길이는 다른 두 변의 길이의 합보다 작아야 합니다.

삼각형의 세 변의 길이가 담긴 배열 `sides`이 매개변수로 주어집니다. 세 변으로 삼각형을 만들 수 있다면 1, 만들 수 없다면 2를 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* `sides`의 원소는 자연수입니다.
* `sides`의 길이는 3입니다.
* 1 ≤ `sides`의 원소 ≤ 1,000

---

##### 입출력 예

| sides            | result |
| ---------------- | ------ |
| \[1, 2, 3\]      | 2      |
| \[3, 6, 2\]      | 2      |
| \[199, 72, 222\] | 1      |

---

##### 입출력 예 설명

입출력 예 #1

* 가장 큰 변인 3이 나머지 두 변의 합 3과 같으므로 삼각형을 완성할 수 없습니다. 따라서 2를 return합니다.

입출력 예 #2

* 가장 큰 변인 6이 나머지 두 변의 합 5보다 크므로 삼각형을 완성할 수 없습니다. 따라서 2를 return합니다.

입출력 예 #3

* 가장 큰 변인 222가 나머지 두 변의 합 271보다 작으므로 삼각형을 완성할 수 있습니다. 따라서 1을 return합니다.

---
## Solution.java

```java
import java.util.*;
class Solution {
    public int solution(int[] sides) {
       Arrays.sort(sides);
        return (sides[0] + sides[1]) > sides[2] ? 1 : 2;
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120889)
---
# 코딩테스트 연습 - 중복된 문자 제거 | 프로그래머스 스쿨



###### 문제 설명

문자열 `my_string`이 매개변수로 주어집니다. `my_string`에서 중복된 문자를 제거하고 하나의 문자만 남긴 문자열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `my_string` ≤ 110
* `my_string`은 대문자, 소문자, 공백으로 구성되어 있습니다.
* 대문자와 소문자를 구분합니다.
* 공백(" ")도 하나의 문자로 구분합니다.
* 중복된 문자 중 가장 앞에 있는 문자를 남깁니다.

---

##### 입출력 예

| my\_string         | result        |
| ------------------ | ------------- |
| "people"           | "peol"        |
| "We are the world" | "We arthwold" |

---

##### 입출력 예 설명

입출력 예 #1

* "people"에서 중복된 문자 "p"와 "e"을 제거한 "peol"을 return합니다.

입출력 예 #2

* "We are the world"에서 중복된 문자 "e", " ", "r" 들을 제거한 "We arthwold"을 return합니다.

---
## Solution.java

```java
import java.util.*;
import java.util.stream.*; //이거 필수임 
class Solution {
    public String solution(String my_string) {
        return Arrays.stream(my_string.split(""))
            .distinct()
            .collect(Collectors.joining(""));
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120888?language=java)

---
# 코딩테스트 연습 - 컨트롤 제트 | 프로그래머스 스쿨


###### 문제 설명

숫자와 "Z"가 공백으로 구분되어 담긴 문자열이 주어집니다. 문자열에 있는 숫자를 차례대로 더하려고 합니다. 이 때 "Z"가 나오면 바로 전에 더했던 숫자를 뺀다는 뜻입니다. 숫자와 "Z"로 이루어진 문자열 `s`가 주어질 때, 머쓱이가 구한 값을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 1 ≤ `s`의 길이 ≤ 200
* \-1,000 < `s`의 원소 중 숫자 < 1,000
* `s`는 숫자, "Z", 공백으로 이루어져 있습니다.
* `s`에 있는 숫자와 "Z"는 서로 공백으로 구분됩니다.
* 연속된 공백은 주어지지 않습니다.
* 0을 제외하고는 0으로 시작하는 숫자는 없습니다.
* `s`는 "Z"로 시작하지 않습니다.
* `s`의 시작과 끝에는 공백이 없습니다.
* "Z"가 연속해서 나오는 경우는 없습니다.

---

##### 입출력 예

| s             | result |
| ------------- | ------ |
| "1 2 Z 3"     | 4      |
| "10 20 30 40" | 100    |
| "10 Z 20 Z 1" | 1      |
| "10 Z 20 Z"   | 0      |
| "-1 -2 -3 Z"  | \-3    |

---

##### 입출력 예 설명

입출력 예 #1

* 본문과 동일합니다.

입출력 예 #2

* 10 + 20 + 30 + 40 = 100을 return 합니다.

입출력 예 #3

* "10 Z 20 Z 1"에서 10 다음 Z, 20 다음 Z로 10, 20이 지워지고 1만 더하여 1을 return 합니다.

입출력 예 #4, #5

설명 생략

---
## Solution.java

```java
import java.util.*;
class Solution {
    public int solution(String s) {
        int a = 0;
        int rs = 0;
        for(String i : s.split(" ")){
            if(i.equals("Z")) {
                rs-=a;
            }
            else{
            rs+=Integer.parseInt(i);
            a=Integer.parseInt(i);
            }
        }
        return rs;
        }
    }

```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120853)