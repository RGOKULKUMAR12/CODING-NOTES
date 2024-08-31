## ***Fibonacci Series***##

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
## ***Next Five Prime***##

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
## ***Prime or Composite***##

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
##