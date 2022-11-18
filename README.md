###  [Task 6 kyu](https://www.codewars.com/kata/5818d00a559ff57a2f000082/train/java)

The Pell sequence is the sequence of integers defined by the initial values

P(0) = 0, P(1) = 1

and the recurrence relation

P(n) = 2 * P(n-1) + P(n-2)

The first few values of P(n) are

0, 1, 2, 5, 12, 29, 70, 169, 408, 985, 2378, 5741, 13860, 33461, 80782, 195025, 470832, ...

Task

Your task is to write a method that returns nth Pell number



### My solution
```Java
import java.math.BigInteger;

public class Solution {
    public static BigInteger pell(int n) {

        BigInteger p0 = BigInteger.valueOf(0);
        BigInteger p1 = BigInteger.valueOf(1);

        BigInteger pn = BigInteger.valueOf(0);

        if (n==0){return BigInteger.valueOf(0);}
        if (n==1){return BigInteger.valueOf(1);}

        for(int i = 2; i <= n; i++){
            pn = p1.multiply(BigInteger.valueOf(2));
            pn = pn.add(p0);
            p0 = p1;
            p1 = pn;
        }

        return pn;

    }
}
```

### Fav solution
```Java
import java.math.BigInteger;

public class Solution {
    public static BigInteger pell(int n) {
        if (n<=2) return BigInteger.valueOf(n);
        BigInteger a = BigInteger.ONE;
        BigInteger b = BigInteger.TWO;
        BigInteger c = BigInteger.ZERO;
        for (int i=3;i<=n;i++) {
            c = a.add(BigInteger.TWO.multiply(b));
            a = b;
            b = c;
        }
        return b;
    }
}

    Best Practices0
        Clever0
                0
                Fork


```
I like this solution because I like it
