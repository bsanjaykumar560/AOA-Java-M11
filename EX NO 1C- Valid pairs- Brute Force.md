
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
