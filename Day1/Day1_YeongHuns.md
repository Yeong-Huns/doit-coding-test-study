# [두 수의 합](https://school.programmers.co.kr/learn/courses/30/lessons/120802)

```java
class Solution {
    
    interface Calculator{
        int calc(int num1, int num2);
    }

    public static int getResult(int num1, int num2, Calculator c){
        return c.calc(num1, num2);
    }

    public int solution(int num1, int num2) {
        return getResult(num1, num2, Integer::sum);
        // Integer::sum == (a, b)-> a + b
    }
    
}
```

<br>

# [두 수의 차](https://school.programmers.co.kr/learn/courses/30/lessons/120803)

```java
class Solution {
    
    interface Calculator{
        int calc(int num1, int num2);
    }

    public static int getResult(int num1, int num2, Calculator c){
        return c.calc(num1, num2);
    }
    
    public int solution(int num1, int num2) {
        return getResult(num1, num2, (a, b)-> a - b);
    }
}
```

<br>

# [두 수의 곱](https://school.programmers.co.kr/learn/courses/30/lessons/120804?language=java)

```java
class Solution {
    
    interface Calculator{
        int calc(int num1, int num2);
    }

    public static int getResult(int num1, int num2, Calculator c){
        return c.calc(num1, num2);
    }
    
    public int solution(int num1, int num2) {
        return getResult(num1, num2, (a, b)-> a * b);
    }
}
```

<br>

# [몫 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/120805)
```java
class Solution {
    
    interface Calculator{
        int calc(int num1, int num2);
    }

    public static int getResult(int num1, int num2, Calculator c){
        return c.calc(num1, num2);
    }
    
    public int solution(int num1, int num2) {
        return getResult(num1, num2, (a, b)-> a / b);
    }
}
```