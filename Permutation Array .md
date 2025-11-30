# Ex9 Finding the Longest Length of Nested Set in a Permutation Array
## DATE: 26-11-2025
## AIM:
To write a program that finds the length of the longest set s[k] defined as s[k] = { nums[k], nums[nums[k]], nums[nums[nums[k]]], … },where the iteration stops before a duplicate element occurs.

The task is to return the maximum size among all such sets.
## Algorithm:
1. Create a visited array to mark elements already used in any set.

2. For each index k, if it is not visited, start building the set S[k].

3. Keep moving to nums[current], marking each element as visited.
   
4. Count each step until you reach a visited element (duplicate).
   
5. Update the maximum count found so far and return it. 

## Program:
```
/*
Program to find the Longest Length of Nested Set in a Permutation Array
Developed by: VEDHASHREE G
RegisterNumber:  212223240171

public class LongestSet {

    // Method to find the longest set length
    public static int arrayNesting(int[] nums) {
        int n = nums.length;
        boolean[] visited = new boolean[n];
        int maxLength = 0;

        for (int i = 0; i < n; i++) {
            if (!visited[i]) {
                int count = 0;
                int current = i;

                while (!visited[current]) {
                    visited[current] = true;
                    current = nums[current];
                    count++;
                }

                if (count > maxLength) {
                    maxLength = count;
                }
            }
        }

        return maxLength;
    }

    public static void main(String[] args) {
        int[] nums = {5, 4, 0, 3, 1, 6, 2};

        int result = arrayNesting(nums);
        System.out.println("Longest Set Length: " + result);
    }
}
*/
```

## Output:
<img width="574" height="131" alt="image" src="https://github.com/user-attachments/assets/cb8db806-0bfa-45ca-a962-bf1208cfcc62" />

## Result:
The program successfully computes the longest length of the nested set s[k] for the given permutation array.
