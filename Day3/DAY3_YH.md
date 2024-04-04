# 나머지 구하기

  

## 문제설명

  

<br>

  

> 📌 정수 `num1`, `num2`가 매개변수로 주어질 때, `num1`를 `num2`로 나눈 나머지를 return 하도록 solution 함수를 완성해주세요.

  

<br>

  

---

  

## 제한사항

  

> - -0 < `num1` ≤ 100

> - -0 < `num2` ≤ 100

  

<br>

  

---

  

## 입출력 예

  

| num1 | num2 | result |

| ---- | ---- | ------ |

| 3    | 2    | 1      |

| 10   | 5    | 0      |

  

<br>

  

---

  

## 입출력 예 설명

  

> 입출력 예 #1

> * `num1`이 3, `num2`가 2이므로 3을 2로 나눈 나머지 1을 return 합니다.

  

> 입출력 예 # 2

> * `num1`이 10, `num2`가 5이므로 10을 5로 나눈 나머지 0을 return 합니다.

  

<br>

  

---

## Solution.java

  

```java

class Solution {
    public int solution(int num1, int num2) {
        return num1 % num2;
    }
}

```

* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120810)
---
# 중앙값 구하기

  

## 문제설명

  

<br>

  

> 📌 중앙값은 어떤 주어진 값들을 크기의 순서대로 정렬했을 때 가장 중앙에 위치하는 값을 의미합니다. 예를 들어 1, 2, 7, 10, 11의 중앙값은 7입니다. 정수 배열 `array`가 매개변수로 주어질 때, 중앙값을 return 하도록 solution 함수를 완성해보세요.

  

<br>

  

---

  

## 제한사항

  

> - `array`의 길이는 홀수입니다.

> - 0 < `array`의 길이 < 100

> - -1,000 < `array`의 원소 < 1,000

  

<br>

  

---

  

## 입출력 예

  

| array             | result |

| ----------------- | ------ |

| [1, 2, 7, 10, 11] | 7      |

| [9, -1, 0]        | 0      |

  

<br>

  

---

  

## 입출력 예 설명

  

> 입출력 예 #1

> * 본문과 동일합니다.

  

> 입출력 예 # 2

> * 9, -1, 0을 오름차순 정렬하면 -1, 0, 9 이고, 가장 중앙에 위치하는 값은 0입니다.

  

<br>

  

---

  
  

## Solution.java

```java
import java.util.*;
class Solution {
    public int solution(int[] array) {
        Arrays.sort(array);
        return array[array.length / 2];
    }
}
```

* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120811)
---
# 짝수는 싫어요

  

## 문제설명

  

<br>

  

> 📌 정수 `n`이 매개변수로 주어질 때, `n` 이하의 홀수가 오름차순으로 담긴 배열을 return하도록 solution 함수를 완성해주세요.

  

<br>

  

---

  

## 제한사항

  

> - 1 ≤ `n` ≤ 100

  
  

<br>

  

---

  

## 입출력 예

  

| n   | result                      |

| --- | --------------------------- |

| 10  | [1, 3, 5, 7, 9]             |

| 15  | [1, 3, 5, 7, 9, 11, 13, 15] |

<br>

  

---

  

## 입출력 예 설명

  

> 입출력 예 #1

> - 10 이하의 홀수가 담긴 배열 [1, 3, 5, 7, 9]를 return합니다.

  

> 입출력 예 # 2

> - 15 이하의 홀수가 담긴 배열 [1, 3, 5, 7, 9, 11, 13, 15]를 return합니다.

  

<br>

  

---

## Solution.java

  

```java

import java.util.*;
class Solution {
    public int[] solution(int n) {
	    List<Integer> list = new ArrayList<>();
	        for(int i = 1; i <= n; i++){
	            if(i % 2 == 1) list.add(i);
	        }
        return list.stream().mapToInt(Integer::intValue).toArray();
    }
}

```

* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120813)
---
# 최빈값 구하기

  

## 문제설명

  

<br>

  

> 📌 최빈값은 주어진 값 중에서 가장 자주 나오는 값을 의미합니다. 정수 배열 `array`가 매개변수로 주어질 때, 최빈값을 return 하도록 solution 함수를 완성해보세요. 최빈값이 여러 개면 -1을 return 합니다.

  

<br>

  

---

  

## 제한사항

  

> - 0 < `array`의 길이 < 100

> - 0 ≤ `array`의 원소 < 1000

  

<br>

  

---

  

## 입출력 예

| array              | result |

| ------------------ | ------ |

| [1, 2, 3, 3, 3, 4] | 3      |

| [1, 1, 2, 2]       | -1     |

| [1]                | 1      |

<br>

  

---

  

## 입출력 예 설명

  

> 입출력 예 #1

> - [1, 2, 3, 3, 3, 4]에서 1은 1개 2는 1개 3은 3개 4는 1개로 최빈값은 3입니다.

  

> 입출력 예 # 2

> - [1, 1, 2, 2]에서 1은 2개 2는 2개로 최빈값이 1, 2입니다. 최빈값이 여러 개이므로 -1을 return 합니다.

  

> 입출력 예 #3

> - [1]에는 1만 있으므로 최빈값은 1입니다.

  

<br>

  

---

## Solution.java

  

```java
import java.util.*;
class Solution {
    public int solution(int[] array){  
    List<int[]> sortedArrayList = sortAndCount(array);  
  
    int max = 0;  
    boolean check = false;  
    int answer = 0;  
  
    for(int[] keyValue : sortedArrayList){  
        System.out.println("key: "+ keyValue[0] + " value: " + keyValue[1]);  
        if(keyValue[1] > max){  
            max = keyValue[1];  
            check = false;  
            answer = keyValue[0];  
        } else if (keyValue[1] == max){  
            check = true;  
        }  
    }  
    return check ? -1 : answer;  
}  
public List<int[]> sortAndCount(int[] array){  
    List<int[]> temp = new ArrayList<>();  
    int count = 0;  
    int[] sortedArray = Arrays.stream(array).sorted().toArray();  
    for(int i = 0; i < sortedArray.length - 1; i++){  
        count++;  
        if(sortedArray[i] != sortedArray[i+1]){  
            temp.add(new int[]{sortedArray[i],count});  
            count = 0;  
        }  
    }  
    temp.add(new int[]{sortedArray[sortedArray.length-1],count+1});  
    return temp;  
}
}
```

* [프로그래머스](https://school.programmers.co.kr/learn/courses/30/lessons/120812?language=java)