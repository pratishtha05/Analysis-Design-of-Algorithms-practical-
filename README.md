# Analysis Design of Algorithms 

> Practical 1:     
  1. <ins>AIM</ins>: Finding peak element in both 1D & 2D array.  
     <ins>WORKING</ins>:
        - For 1D array:  
            1. The function peakElement1D uses binary search to find a peak element in a 1D array.  
            2. It compares the middle element (mid) with its neighbors:
               - If arr[mid] < arr[mid - 1], move left (high = mid - 1).
               - If arr[mid] < arr[mid + 1], move right (low = mid + 1).
               - Otherwise, arr[mid] is a peak and is returned.  
           - Time complexity: O(logn)   
             Space Complexity: O(1)  
        - For 2D array:  
            1. It uses a binary search on columns to find a peak element in a 2D matrix  
            2. In each step:
               - It finds the maximum element in the mid-column (findMaxInColumn).
               - Checks if it is greater than its neighbors (left, right, top, bottom).
               - If it is a peak, it returns the element.
               - Otherwise, it moves left or right in the matrix to continue the search.  
          - Time complexity: O(mlogn)   
            Space Complexity: O(1) 

      <ins>Output</ins>:  
      For the given 3×3 matrix:  
      1   2   3<br>
      10  5   9<br>
      6   7   5<br>
      Peak element: 7  
---
---  

2. <ins>AIM</ins>: Magic square   
   <ins>WORKING</ins>:  
   1. Start at the middle of the first row (p = 0, q = n/2).
      - Place 1 at this position.
   2. For each next number (from 2 to n²):
      - Move up-left (p-1, q-1).
      - If the new position goes out of bounds:
         - Wrap around to the last row if p < 0.
         - Wrap around to the last column if q < 0.
      - If the new position is already filled, move directly down (p+1).
   3. Repeat until the entire matrix is filled.  
   - Time complexity: O(n^2)  
     Space complexity: O(n^2)

   <ins>Output</ins>:  
   enter the value of n: 3  
   Magic Square generated.  
   618  
   753  
   294  

---
---  

3. <ins>AIM</ins>: Calculating a^n  
   <ins>WORKING</ins>:  
   The function power(a, n) calculates a^n efficiently using divide and conquer:

   1. Base Case:
      - If n = 0, return 1 (since any number raised to power 0 is 1).
   2. Recursive Step:
      - Compute halfPower = power(a, n / 2) recursively.
      - If n is even:
         - aⁿ = (a^(n/2)) × (a^(n/2))
      - If n is odd:
         - aⁿ = a × (a^(n/2)) × (a^(n/2))  
   - Time complexity: O(logn)  
     Space complexity: O(logn)

   <ins>Output</ins>:  
   Enter the base (a): 2  
   Enter the exponent (n): 5  
   2^5 = 32  
---
---  

4. <ins>AIM</ins>: Calculate the similarity between two text documents (cosine similarity)  
   <ins>WORKING</ins>:
   The function power(a, n) calculates a^n efficiently using divide and conquer:

   1. Stop Words Removal:
      - The program maintains a set of common stop words (e.g., "a", "the", "and", "is") which are ignored during processing.
   2. Building a Dictionary:
      - It reads docA.txt, extracts words, and ignores stop words.
      - Each unique word is stored in a dictionary (map<int, string>), where:
         - Key: Unique index for the word.
         - Value: The actual word.  
   3. Creating Frequency Vectors:  
      - Two vectors are created:  
         - wordsFreqA (for docA.txt)
         - wordsFreqB (for docB.txt)  
      - These store the frequency of each dictionary word in both documents.  
   4. Calculating Cosine Similarity:  
      - The similarity is computed using the cosine similarity formula  
      - The final similarity score is converted into a percentage.  
   - Time complexity: O(N + M + D)  
     Space complexity: O(N + M + D)  
     ( where N = words in docA.txt, M = words in docB.txt and D = size of dictionary ) 

   <ins>Output</ins>:  
   The dictionary:  
   1: quick  
   2: brown  
   3: fox  
   4: jumps  
   5: over  
   6: lazy  
   7: dog  

   freq vector A: 1 1 1 1 1 1 1

   freq vector B: 0 1 1 0 0 1 1

   dot product: 3  
   mag of A: 7  mag of B: 3  
   sqrt values:  
   mag of A: 2.64575  mag of B: 1.73205  
   Similarity Percentage: 65.31%
