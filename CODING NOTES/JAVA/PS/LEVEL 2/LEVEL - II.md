## ***Fibonacci Series*** ##

```java
import java.util.*;

class Main {
  
    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        
        if (n1 <= 0) {
            System.out.println("Invalid");
        } else {
            int a = 0, num1 = 0, num2 = 1;
            for (int i = 1; i <= n1; i++) {
                System.out.print(num1 + ",");
                a = num1 + num2;
                num1 = num2;
                num2 = a;
            }
        }
    }
}

```

| INPUT | OUPUT          |
| ----- | -------------- |
| 7     | 0,1,1,2,3,5,8, |
| 4     | 0,1,1,2,       |
| -1    | Invalid        |

---
## ***Next Five Prime*** ##

```java
import java.util.*;

class Main {

    public static int is_prime(int n) {
        if (n == 0)
            return 0;
        if (n <= 3)
            return 1;
        for (int i = 2; i <= n / 2; i++) {
            if (n % i == 0)
                return 0;
        }
        return 1;
    }

    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        
        int count = 1;
        while (count <= 5) {
            n1++;
            if (is_prime(n1) == 1) {
                System.out.println(n1);
                count++;
            }
        }
    }
}

```

| INPUT | OUTPUT                          |
| ----- | ------------------------------- |
| 99    | 101<br>103<br>107<br>109<br>113 |
| 20    | 23<br>29<br>31<br>37<br>41      |

---
## ***Prime or Composite*** ##

```java
import java.util.*;

class Main {

    public static int is_prime(int n) {
        if (n == 0)
            return 0;
        if (n <= 3)
            return 1;
        for (int i = 2; i <= n / 2; i++) {
            if (n % i == 0)
                return 0;
        }
        return 1;
    }

    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        
        if (is_prime(n1) == 1) {
            System.out.println(n1 + " IS A PRIME");
        } else {
            System.out.println(n1 + " IS A COMPOSITE");
        }
    }
}

```

---
## ***Series and Sum*** ##

```java
import java.util.*;

class Main {
  
    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        int s = n.nextInt();
        int ans = 0, sum = 0;
        
        for (int i = 1; i <= s; i++) {
            ans = 0;
            for (int j = 1; j <= i; j++) {
                ans = ans * 10 + n1;
            }
            sum += ans;
            System.out.print(ans);
            if (i < s) {
                System.out.print("+");
            }
        }
        
        System.out.println("\n" + sum);
    }
}

```

| INPUT   | OUTPUT                                |
| ------- | ------------------------------------- |
| 2 <br>5 | 2 + 22 + 222 + 2222 + 22222 <br>24690 |
| 3<br>4  | 3+33+333+3333<br>3702                 |

---
## ***Divisors Sum Equality*** ##

```java
import java.util.*;

class Main {

    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        int sum = 0;
        
        for (int i = 1; i <= n1 / 2; i++) {
            if (n1 % i == 0) {
                System.out.print(i + " ");
                sum += i;
            }
        }
        
        System.out.print("\n");
        System.out.println(sum);
        
        if (sum == n1) {
            System.out.println(n1 + " is an Equal Number");
        } else {
            System.out.println(n1 + " is not an Equal Number");
        }
    }
}

```

| INPUT | OUTPUT                                                  |
| ----- | ------------------------------------------------------- |
| 6     | 1 2 3 <br>6<br>6 is an Equal Number                     |
| 42    | 1 2 3 6 7 14 21 <br>54<br>42 is not an Equal Number<br> |

---
## ***Abudant Number*** ##

```java
import java.util.*;

class Main {

    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        int sum = 0;
        
        for (int i = 1; i <= n1 / 2; i++) {
            if (n1 % i == 0) {
                sum += i;
            }
        }
        
        if (sum > n1) {
            System.out.println(n1 + " is an Abudant Number");
        } else {
            System.out.println(n1 + " is not an Abudant Number");
        }
    }
}

```

| INPUT | OUTPUT                      |
| ----- | --------------------------- |
| 12    | 12 is an Abudant Number     |
| 13    | 13 is not an Abudant Number |

---
## ***Count of Leap Years and Non-Leap Years in a Decade*** ##

```java
import java.util.*;

class Main {

    public static int is_leap(int n) {
        if ((n % 4 == 0 && n % 100 != 0) || n % 400 == 0)
            return 1;
        return 0;
    } 
    
    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        if (is_leap(n1) == 1)
            System.out.println(n1 + " is a leap year");
        else
            System.out.println(n1 + " is not a leap year");
        
        int leap = 0, non_leap = 0;
        
        for (int i = n1 + 1; i <= n1 + 10; i++) {
            if (is_leap(i) == 1)
                leap++;
            else
                non_leap++;
        }
        
        System.out.println("Leap Years: " + leap);
        System.out.println("Non-Leap Years: " + non_leap);
    }
}

```

| INPUT | OUTPUT                                                           |
| ----- | ---------------------------------------------------------------- |
| 2024  | 2024 is a Leap Year. <br>Leap Years: 2 <br>Non-Leap Years: 8     |
| 2010  | 2010 is not a Leap Year.<br> Leap Years: 3 <br>Non-Leap Years: 7 |

---
## ***Geometric Series*** ##

```java
import java.util.*;

class Main {

    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        float b = 1.0f, sum = 0.0f;
        
        if (n1 < 0) {
            System.out.print("0.00");
            System.exit(0);
        }
        
        for (int i = 1; i <= n1; i++) {
            sum += 1.0 / b;
            b *= 2;
        }
        
        System.out.printf("%.2f", sum);
    }
}


```

| INPUT | OUTPUT  |
| ----- | ------- |
| 3     | 1.75    |
| -2    | Invalid |

---
## ***Sum of N Square Numbers*** ##

```java
import java.util.*;

class Main {

    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        if (n1 <= 0) {
            System.out.print("Invalid");
            System.exit(0);
        }
        
        int sum = 0;
        for (int i = 1; i <= n1; i++) {
            sum += (i * i);
        }
        
        System.out.println(sum);
    }
}

```

| INPUT | OUTPUT  |
| ----- | ------- |
| 5     | 55      |
| -1    | Invalid |

---
## ***Harmonic Series*** ##

```java
import java.util.*;

class Main {

    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        float ans = 0.0f;
        
        if (n1 <= 0) {
            System.out.print("Invalid");
            System.exit(0);
        }
        
        for (int i = 1; i <= n1; i++) {
            ans += 1.0 / i;
        }
        
        System.out.printf("%.2f", ans);
    }
}

```

| INPUT | OUTPUT  |
| ----- | ------- |
| 4     | 2.08    |
| -1    | Invalid |

---

>[!Tip]
>- TO FIND NO OF DIGITS IN AN NUMBER
> 	    `int count  = (int)Math.floor(Math.log10(n1) + 1);`  `

---
## ***Swapping First and Last*** ##

```java
import java.util.*;

class Main {
  
    public static void main(String... args) {
        Scanner n = new Scanner(System.in);
        
        int n1 = n.nextInt();
        int digits = (int) Math.floor(Math.log10(n1) + 1);
        int power = (int) Math.pow(10, digits - 1); 
        
        int first = n1 / power;
        int last = n1 % 10;
        
        first = (first + last) - (last = first);
        
        System.out.println(first + " " + last);
        
        int fina = first * power + ((n1 % power) / 10) * 10 + last;
        
        System.out.println(fina);
    }
}


```

| INPUT | OUTPUT  |
| ----- | ------- |
| 5     | 55      |
| -1    | Invalid |
 >[!Tip]
 >	- To swap two Integers
 >		` first = (first + last) - (last = first);`

---
