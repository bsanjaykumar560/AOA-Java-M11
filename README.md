
# EX 1A Print All Numbers 
## DATE: 6.8.25
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





# EX 1B Power of 2
## DATE: 19.8.25
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





# EX 1C Valid Pairs using Brute Force Approach
## DATE: 21.8.26
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.

## Algorithm
1. Start

2. Read integer n (size of array).

3. Create an array nums of size n.

4. Read all n integers into the array nums.

5. Read integer k.

6. Initialize count = 0.

7. For each index i from 0 to n − 1: For each index j from i + 1 to n − 1: If abs(nums[i] − nums[j]) == k, then: Increment count by 1.

8. Print the value of count.

9. Stop  

## Program:
```
/*
Program to implement Reverse a String
Developed by: MUKESH R
Register Number: 212223240100
*/
import java.util.Scanner;
public class CountPairsWithDifference {
    public static int countKDifference(int[] nums, int k) {
        int count=0;
        for (int i=0;i<nums.length;i++)
        {
            for(int j=i+1;j<nums.length;j++)
            {
                if (Math.abs(nums[i]-nums[j])==k)
                {
                    count++;
                }
            }
        }
        
        
        return count;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        int k = sc.nextInt();
        int result = countKDifference(nums, k);
        System.out.println(result);
        sc.close();
    }
}

```

## Output:
<img width="445" height="432" alt="image" src="https://github.com/user-attachments/assets/546e14bb-9b67-45d2-bb10-922c693b65ff" />



## Result:
The program successfully implemented and the expected output is verified.




# EX 1D Sorted Array using Divide and Conquer Approach.
## DATE: 11.9.25
## AIM:
To write a Java program to for given constraints.
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

## Algorithm
1. Read two sorted arrays nums1 and nums2.


2. Set two pointers p1 = 0 and p2 = 0.


3. Repeatedly pick the smaller element from the two arrays (like merge sort).


4. Stop when you reach the middle position(s) of the merged array.


5. If total length is odd → median is the middle element.


6. If total length is even → median is the average of the two middle elements.



## Program:
```
/*
Program to implement Reverse a String
Developed by: MUKESH R
Register Number: 212223240100
*/
import java.util.Scanner;

public class Solution {
    private int p1 = 0, p2 = 0;

    
    private int getMin(int[] nums1, int[] nums2) {
        if (p1 < nums1.length && p2 < nums2.length) {
            return nums1[p1] < nums2[p2] ? nums1[p1++] : nums2[p2++];
        } else if (p1 < nums1.length) {
            return nums1[p1++];
        } else if (p2 < nums2.length) {
            return nums2[p2++];
        }
        return -1; // Should not reach here if input is valid
    }

    
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
       int m =nums1.length,n=nums2.length;
       if((m+n)%2==0){
           for(int i=0;i<(m+n)/2-1;i++){
               int tmp =getMin(nums1,nums2);
           }
           return (double) (getMin(nums1,nums2)+getMin(nums1,nums2))/2;
       }
       else{
           for(int i=0;i<(m+n)/2;i++){
               int tmp=getMin(nums1,nums2);
           }
       } return getMin(nums1,nums2);
    }

    
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        
        int m = sc.nextInt();
        int[] nums1 = new int[m];
        for (int i = 0; i < m; i++) {
            nums1[i] = sc.nextInt();
        }

        
        int n = sc.nextInt();
        int[] nums2 = new int[n];
          for (int i = 0; i < n; i++) {
            nums2[i] = sc.nextInt();
        }

        
        double median = sol.findMedianSortedArrays(nums1, nums2);
        System.out.println("Median of the two sorted arrays = " + median);
        
        sc.close();
    }
}
```




## Output:
<img width="913" height="478" alt="image" src="https://github.com/user-attachments/assets/e14072f6-cac9-4f6d-843b-3e412e45556f" />



## Result:
The program successfully implemented and the expected output is verified.


# EX 1E Integer Multiplication using Divide and Conquer Approach(Strassen’s algorithm).
## DATE: 11.9.25
## AIM:
To write a Java program to for given constraints.
You are given two square matrices A and B of size n × n (where n is a power of 2). Your task is to compute their matrix product using Strassen’s Matrix Multiplication algorithm and return the resulting matrix.

Unlike traditional matrix multiplication which takes O(n3)O(n^3)O(n3) time, Strassen’s algorithm improves this by reducing the number of recursive multiplications from 8 to 7, achieving approximately O(n2.81)O(n^{2.81})O(n2.81) complexity.

## Algorithm
1. Read matrix size n and matrices A and B.

2. If n = 1, multiply the single elements and return.

3. Split both matrices into four submatrices (A11, A12, A21, A22 and B11, B12, B21, B22).

4. Compute the seven Strassen products M1 to M7 using recursive calls.

5. Form the four result blocks C11, C12, C21, C22 using M1–M7.

6. Combine the four blocks into the final matrix C and print it.

## Program:
```
/*
Program to implement Reverse a String
Developed by: MUKESH R
Register Number: 212223240100
*/
import java.util.Scanner;

public class StrassenMatrix {

    static int[][] add(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] + B[i][j];
        return C;
        
    }
    static int[][] subtract(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] - B[i][j];
        return C;
    }

    static int[][] strassen(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        
        if (n == 1) {
            C[0][0] = A[0][0] * B[0][0];
            return C;
        }

        int newSize = n / 2;
        int[][] A11 = new int[newSize][newSize];
        int[][] A12 = new int[newSize][newSize];
        int[][] A21 = new int[newSize][newSize];
        int[][] A22 = new int[newSize][newSize];
        int[][] B11 = new int[newSize][newSize];
        int[][] B12 = new int[newSize][newSize];
        int[][] B21 = new int[newSize][newSize];
        int[][] B22 = new int[newSize][newSize];

       
        
        for (int i = 0; i < newSize; i++) {
            for (int j = 0; j < newSize; j++) {
                A11[i][j] = A[i][j];
                A12[i][j] = A[i][j + newSize];
                A21[i][j] = A[i + newSize][j];
                A22[i][j] = A[i + newSize][j + newSize];

                B11[i][j] = B[i][j];
                B12[i][j] = B[i][j + newSize];
                B21[i][j] = B[i + newSize][j];
                B22[i][j] = B[i + newSize][j + newSize];
            }
        }

        // Compute M1 to M7
        int[][] M1 = strassen(add(A11, A22), add(B11, B22));
        int[][] M2 = strassen(add(A21, A22), B11);
        int[][] M3 = strassen(A11, subtract(B12, B22));
        int[][] M4 = strassen(A22, subtract(B21, B11));
        int[][] M5 = strassen(add(A11, A12), B22);
        int[][] M6 = strassen(subtract(A21, A11), add(B11, B12));
        int[][] M7 = strassen(subtract(A12, A22), add(B21, B22));

        int[][] C11 = add(subtract(add(M1, M4), M5), M7);
        int[][] C12 = add(M3, M5);
        int[][] C21 = add(M2, M4);
        int[][] C22 = add(subtract(add(M1, M3), M2), M6);

        for (int i = 0; i < newSize; i++) {
            for (int j = 0; j < newSize; j++) {
                C[i][j] = C11[i][j];
                C[i][j + newSize] = C12[i][j];
                C[i + newSize][j] = C21[i][j];
                C[i + newSize][j + newSize] = C22[i][j];
            }
        }

        return C;
    }

    static void printMatrix(int[][] matrix) {
        for (int[] row : matrix) {
            for (int val : row)
                System.out.print(val + " ");
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();

        int[][] A = new int[n][n];
        int[][] B = new int[n][n];

        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                A[i][j] = sc.nextInt();

        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                B[i][j] = sc.nextInt();

        int[][] result = strassen(A, B);

        System.out.println("Result of Strassen Matrix Multiplication:");
        printMatrix(result);
    }
}
```

## Output:
<img width="906" height="941" alt="image" src="https://github.com/user-attachments/assets/8addd8f3-0d51-480a-865c-e562585e7d78" />



## Result:
The program successfully implemented and the expected output is verified.





## Result:
The program successfully print all the numbers from 1 to N. 
