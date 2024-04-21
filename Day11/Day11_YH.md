# 코딩테스트 연습 - 주사위의 개수 | 프로그래머스 스쿨




###### 문제 설명

머쓱이는 직육면체 모양의 상자를 하나 가지고 있는데 이 상자에 정육면체 모양의 주사위를 최대한 많이 채우고 싶습니다. 상자의 가로, 세로, 높이가 저장되어있는 배열 `box`와 주사위 모서리의 길이 정수 `n`이 매개변수로 주어졌을 때, 상자에 들어갈 수 있는 주사위의 최대 개수를 return 하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* `box`의 길이는 3입니다.
* `box[0]` \= 상자의 가로 길이
* `box[1]` \= 상자의 세로 길이
* `box[2]` \= 상자의 높이 길이
* 1 ≤ `box`의 원소 ≤ 100
* 1 ≤ `n` ≤ 50
* `n` ≤ `box`의 원소
* 주사위는 상자와 평행하게 넣습니다.

---

##### 입출력 예

| box          | n | result |
| ------------ | - | ------ |
| \[1, 1, 1\]  | 1 | 1      |
| \[10, 8, 6\] | 3 | 12     |

##### 입출력 예 설명

입출력 예 #1

* 상자의 크기가 가로 1, 세로 1, 높이 1이므로 모서리의 길이가 1인 주사위는 1개 들어갈 수 있습니다.

입출력 예 #2

* 상자의 크기가 가로 10, 세로 8, 높이 6이므로 모서리의 길이가 3인 주사위는 12개 들어갈 수 있습니다.
---
## Solution.js

```javaScript
let solution = (box, n) => box.map(a=>~~(a/n)).reduce((a,b)=>a*b);
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120845?language=java)

---
# 코딩테스트 연습 - 최댓값 만들기(1) | 프로그래머스 스쿨



###### 문제 설명

정수 배열 `numbers`가 매개변수로 주어집니다. `numbers`의 원소 중 두 개를 곱해 만들 수 있는 최댓값을 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 0 ≤ `numbers`의 원소 ≤ 10,000
* 2 ≤ `numbers`의 길이 ≤ 100

---

##### 입출력 예

| numbers                 | result |
| ----------------------- | ------ |
| \[1, 2, 3, 4, 5\]       | 20     |
| \[0, 31, 24, 10, 1, 9\] | 744    |

---

##### 입출력 예 설명

입출력 예 #1

* 두 수의 곱중 최댓값은 4 \* 5 = 20 입니다.

입출력 예 #1

* 두 수의 곱중 최댓값은 31 \* 24 = 744 입니다.

---
## Solution.java

```java
import java.util.*;
class Solution {
    public int solution(int[] numbers) {
        Arrays.sort(numbers);
        return numbers[numbers.length-1]*numbers[numbers.length-2];
    }
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120847?language=java)

---
# 코딩테스트 연습 - 팩토리얼 | 프로그래머스 스쿨


###### 문제 설명

`i`팩토리얼 (i!)은 1부터 i까지 정수의 곱을 의미합니다. 예를들어 5! = 5 \* 4 \* 3 \* 2 \* 1 = 120 입니다. 정수 n이 주어질 때 다음 조건을 만족하는 가장 큰 정수 i를 return 하도록 solution 함수를 완성해주세요.

* i! ≤ n

---

##### 제한사항

* 0 < `n` ≤ 3,628,800

---

##### 입출력 예

| n       | result |
| ------- | ------ |
| 3628800 | 10     |
| 7       | 3      |

---

##### 입출력 예 설명

입출력 예 #1

* 10! = 3,628,800입니다. `n`이 3628800이므로 최대 팩토리얼인 10을 return 합니다.

입출력 예 #2

* 3! = 6, 4! = 24입니다. `n`이 7이므로, 7 이하의 최대 팩토리얼인 3을 return 합니다.

---
## Solution.js

```javascript
function solution(n) {
    let count = 2
    while(true){
        let sum = 1;
        for(let i = count; i >= 1; i--)
            sum*=i;
        if(sum>n) break;
        count++;
    }
    return count -1;
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120848?language=java)

---

# 코딩테스트 연습 - 합성수 찾기 | 프로그래머스 스쿨



###### 문제 설명

약수의 개수가 세 개 이상인 수를 합성수라고 합니다. 자연수 `n`이 매개변수로 주어질 때 `n`이하의 합성수의 개수를 return하도록 solution 함수를 완성해주세요.

---

##### 제한사항

* 1 ≤ `n` ≤ 100

---

##### 입출력 예

| n  | result |
| -- | ------ |
| 10 | 5      |
| 15 | 8      |

---

##### 입출력 예 설명

입출력 예 #1

* 10 이하 합성수는 4, 6, 8, 9, 10 로 5개입니다. 따라서 5를 return합니다.

입출력 예 #1

* 15 이하 합성수는 4, 6, 8, 9, 10, 12, 14, 15 로 8개입니다. 따라서 8을 return합니다.
 
---
## Solution.js

```javascript
function solution(n) {
    return Array(n)
    .fill()
    .map((_,i)=>i+1)
    .filter(a=>{
        let cnt = 0;
        for(let i = 1; i <= a; i++){
            if(a%i==0)cnt++
        }
        if(cnt>=3)return a
    }).length;
}
```

---
* [Read Original](https://school.programmers.co.kr/learn/courses/30/lessons/120846?language=java) 