# 코딩테스트 연습 - 문자 반복 출력하기 | 프로그래머스 스쿨




###### 문제 설명

문자열 `my_string`과 정수 `n`이 매개변수로 주어질 때, `my_string`에 들어있는 각 문자를 `n`만큼 반복한 문자열을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 2 ≤ `my_string` 길이 ≤ 5
* 2 ≤ `n` ≤ 10
* "my\_string"은 영어 대소문자로 이루어져 있습니다.

---

##### 입출력 예

| my\_string | n | result            |
| ---------- | - | ----------------- |
| "hello"    | 3 | "hhheeellllllooo" |

---

##### 입출력 예 설명

입출력 예 #1

* "hello"의 각 문자를 세 번씩 반복한 "hhheeellllllooo"를 return 합니다.
---
## Solution.java

```java
class Solution {
    public String solution(String string, int times) {
        return Stream.of(string)
                .flatMap(e-> Arrays.stream(e.split("")))
                .map(a-> String.valueOf(a).repeat(times))
                .reduce("", (a,b)->a+b);
    }
}
```
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120825?language=java)


---

# 코딩테스트 연습 - 문자열 뒤집기 | 프로그래머스 스쿨

###### 문제 설명

문자열 `my_string`이 매개변수로 주어집니다. `my_string`을 거꾸로 뒤집은 문자열을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `my_string`의 길이 ≤ 1,000

---

##### 입출력 예

| my\_string | return  |
| ---------- | ------- |
| "jaron"    | "noraj" |
| "bread"    | "daerb" |

---

##### 입출력 예 설명

입출력 예 #1

* `my_string`이 "jaron"이므로 거꾸로 뒤집은 "noraj"를 return합니다.

입출력 예 #2

* `my_string`이 "bread"이므로 거꾸로 뒤집은 "daerb"를 return합니다.
---
## Solution.java

```java
class Solution {
    public String solution(String my_string) {
        return new StringBuilder(my_string).reverse().toString();
    }
}
```
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120822)

---
# 코딩테스트 연습 - 직각삼각형 출력하기 | 프로그래머스 스쿨

[Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120823?language=java)


###### 문제 설명

"\*"의 높이와 너비를 1이라고 했을 때, "\*"을 이용해 직각 이등변 삼각형을 그리려고합니다. 정수 n 이 주어지면 높이와 너비가 n 인 직각 이등변 삼각형을 출력하도록 코드를 작성해보세요.

---

##### 제한사항

* 1 ≤ `n` ≤ 10

---

##### 입출력 예

입력 #1

```angelscript
3

```

출력 #1

```asciidoc
*
**
***

```

##### 입출력 예 설명

입출력 예 #1

* n이 3이므로 첫째 줄에 \* 1개, 둘째 줄에 \* 2개, 셋째 줄에 \* 3개를 출력합니다.
---
## Solution.java

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int count = 0;
        for(int i = 0; i < n; i++){
            System.out.print("*");
            if(i == count){
                System.out.println();
                count++;
                if(count == n){break;}
                i = -1;
            }
        }
    }
}
```
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120823?language=java)

---
# 코딩테스트 연습 - 짝수 홀수 개수 | 프로그래머스 스쿨




###### 문제 설명

정수가 담긴 리스트 `num_list`가 주어질 때, `num_list`의 원소 중 짝수와 홀수의 개수를 담은 배열을 return 하도록 solution 함수를 완성해보세요.

---

##### 제한사항

* 1 ≤ `num_list`의 길이 ≤ 100
* 0 ≤ `num_list`의 원소 ≤ 1,000

---

##### 입출력 예

| num\_list         | result   |
| ----------------- | -------- |
| \[1, 2, 3, 4, 5\] | \[2, 3\] |
| \[1, 3, 5, 7\]    | \[0, 4\] |

---

##### 입출력 예 설명

입출력 예 #1

* \[1, 2, 3, 4, 5\]에는 짝수가 2, 4로 두 개, 홀수가 1, 3, 5로 세 개 있습니다.

입출력 예 #2

* \[1, 3, 5, 7\]에는 짝수가 없고 홀수가 네 개 있습니다.

4개의 제출

새로고침

제출일시

언어

채점 내역

1

---
## Solution.java

```java
class Solution {
    public int[] solution(int[] num_list) {
        int[] answer = {0, 0};
        for(int i : num_list)answer[i%2]++;    
        return answer;
    }
}
```
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120824)