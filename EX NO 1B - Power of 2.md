
# EX 1B Power of 2
## DATE: 19.8.26
## AIM:
To write a Java program to for given constraints.Given an integer n, return true if it is a power of two. Otherwise, return false.

An integer n is a power of two, if there exists an integer x such that n == 2^x.

## Algorithm:
1. Start

2. Read an integer value n from the user.

3. If n ≤ 0, then: Output false and stop

4. Compute the value of (n & (n - 1)).

5. If the result is 0, then: Output true else: Output false

6. Stop

## Program:
```
/*
Program to implement Reverse a String
Developed by: MUKESH R
Register Number: 212223240100
*/
import java.util.Scanner;
public class Solution {

    public static boolean isPowerOfTwo(int n) {
        if (n <= 0) return false;
        return (n & (n - 1)) == 0;
     
     
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution sol = new Solution();
        int n = scanner.nextInt();

        boolean result = sol.isPowerOfTwo(n);
        System.out.println(result);

        scanner.close();
    }
}

```

## Output:

<img width="427" height="336" alt="image" src="https://github.com/user-attachments/assets/7e8d82ce-7c58-4a00-93cb-a412d08d533e" />


## Result:
The program successfully implemented and the expected output is verified.
