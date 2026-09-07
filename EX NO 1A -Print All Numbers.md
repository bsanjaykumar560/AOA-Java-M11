
# EX 1A Print All Numbers 
## DATE: 9.9.26
## AIM:
To Write a Java program that takes an integer input N from the user and prints all the numbers from 1 to N, separated by spaces, on a single line..

## Algorithm
1. Start

2. Read integer N from the user.

3. If N ≤ 0: Print "Invalid input. N must be greater than 0." and stop

4. Set counter i = 1

5. Repeat while i ≤ N: Print i if i < N, print a space and increment i by 1

6. Stop

## Program:
```
/*
Program to implement Reverse a String
Developed by: MUKESH R
Register Number: 212223240100
*/
import java.util.Scanner;
public class PrintNumbers {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();

        if (N <= 0) {
            System.out.println("Invalid input. N must be greater than 0.");
        } else {
            for (int i = 1; i <= N; i++) {
                System.out.print(i);
                if (i < N) {
                    System.out.print(" ");
                }
            }
        }
    }
}

```

## Output:

<img width="460" height="296" alt="image" src="https://github.com/user-attachments/assets/b64c53c0-5e5e-4640-b891-4b83671849ad" />


## Result:
The program successfully print all the numbers from 1 to N. 
