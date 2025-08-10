# Problem Statement
- You are given an integer `n`. We reorder the digits in any order (including the original order) such that the leading digit is not zero.
  
  Return `true` *if and only if we can do this so that the resulting number is a power of two*.
   
  **Example 1:**
  
  ```
  **Input:** n = 1
  **Output:** true
  ```
  
  **Example 2:**
  
  ```
  **Input:** n = 10
  **Output:** false
  ```
  
   
  
  **Constraints:**
- `1 <= n <= 109`
-
- # Solution
- ```python
  class Solution:
      def reorderedPowerOf2(self, n: int) -> bool:
          def count_digits(num):
              count = [0] * 10
              while num:
                  num, digit = divmod(num, 10)
                  count[digit] += 1
              return count
  
          input_digit_count = count_digits(n)
          power_of_two = 1
          while power_of_two <= 10**9:
              if count_digits(power_of_two) == input_digit_count:
                  return True
              power_of_two <<= 1
        
          return False
  ```
- # Time Complexity :O(1)
-