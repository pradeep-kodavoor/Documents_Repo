Algorithms - Steps to be performed for accomplishing a particular task.
Real time example: Steps involved in Preparing Tea.

1. Boil Water
2. Add a teabag to a cup
3. Pour the boiling water into the cup
4. Remove the teabag when tea is ready
5. Add the desire amount of milk to the cup
6. Add the desire amount of sugar to the cup
7. Stir the contents of the cup with a spoon

There can be many different ways of preparing tea, but this is one of them.
Similarly there can be many algorithms that accomplish the same task.
There can be many implementations of the same algorithm

Algorithm is not an implementation
Algorithm describes the steps that are performed
Implementation is the code that is written to perform the algorithm.

Ex. with respect to Preparing tea

Need for Big O Notation:

Same implementation can take different time when it is run on Super Computer and Normal Computer.
Hence for determing performance based on number of steps Big O Notation was introduced, where performance is measured by taking 
number of steps into account.

Big O Notation -
Determines performance of the data structures
Describes the complexity of the data structure
Tells us how well an algorithm scales as the input increases.
Worst case is used to determine the time complexity of the algorithm.

O(1) - Constant time - No matter how many elements u have in your data structures, Algorithm always perform same number of operations
O(logn)(base 2) - Logarithamic - Slows rises as the number of elements increases Ex: Binary Search
O(n) - Linear - Descreases the performance as the elements decreases. Ex: For Loop, While Loop
O(nlogn)(base 2) - n log-star-n Logarithamic - Slows rises as the number of elements increases Ex: Binary Search
O(n^2) - Quadratic - As the number of elements increase, performance becomes very very low. Ex: Loop within loop
O(c^n) - Exponential - Recusrive calls over n and loop over c in it.
O(n!) - Factorial - Looping over n and recursive call in the loop for (n-1) elements

![alt text](https://en.wikipedia.org/wiki/Big_O_notation#/media/File:Comparison_computational_complexity.svg)

Sort Algorithms:

Bubble Sort 
  - Performance degrades quickly as number of elements grows.
  - Grows the sorted partition from right to left
Algorithm:
  - Larger value in an array bubbles up to the top on each iteration.
  - During each iteration, an element is compared with the next one and swaped if an element is greater than the next one.
  - End of each iteration an element would be in correct position

Performance:
  - In-place algorithm, logical partition of array is done. Extra memory is not required for partition.
  - O(n^2) - Quadratic - Time Complexity
  - It will take 100 steps to sort 10 elements, 10,000 steps to sort 100 elements so on..
  - Algorithm degrades quickly as number of elements increases.
  - Stable Algorithm.

Stable vs Unstable Algorithm
  - Stable: Preserves relative ordering of duplicate items
    Ex: If an array has 2 elements with value, its ordering is unaltered.
  - Unstable: Does not preserve relative ordering of duplicate items
    Ex: If an array has 2 elements with value, its ordering is changed.

Selection Sort
  - Divides the array into sorted and unsorted partition
  - Grows the sorted partition from right to left
  - Traverse the elements of Unsorted partition and find the largest element
  - Swap the largest element with the last element

Performance:
  - In-place algorithm, logical partition of array is done. Extra memory is not required for partition.
  - O(n^2) - Quadratic - Time Complexity
  - It will take 100 steps to sort 10 elements, 10,000 steps to sort 100 elements so on..
  - Algorithm degrades quickly as number of elements increases.
  - Unstable Algorithm.
  
 Insertion Sort
  - Divides the array into sorted and unsorted partition
  - Grows the sorted partition from left to right
  - Starts by considering element at position 1 as element in sorted partition.
  - On Each iteration, first element from unsorted partition is taken and inserted into sorted partition.
  - We compare the value to be inserted with values in the sorted partition.
  - Position of insertion is determined by comparing values in the sorted partition against new element.
  - If new element is less than the elements in the sorted partition, elements are shifted in the sorted partition.
  
Implementation:
  - Consider first element (index - 0) as sorted partition.
  - Hence start from  firstUnsortedIndex = 1 -> Second element in the array. 
  - Element at input[firstUnsortedIndex] is the element to be inserted.
  - Now compare the elements in the sorted partition starting from right to left with the new element
  - if new element is less than the element in sorted partition shift that particular element in sorted partition to its right.
  - Stop the traversal when we find an element that is greater than new element.
  - Place the new element in that position.
  - Repeat the loop till all elements are inserted into it correct position.

Performance:
  - In-place algorithm, logical partition of array is done. Extra memory is not required for partition.
  - O(n^2) - Quadratic - Time Complexity
  - It will take 100 steps to sort 10 elements, 10,000 steps to sort 100 elements so on..
  - Algorithm degrades quickly as number of elements increases.
  - Unstable Algorithm.
  
Shell Sort
  - Variation of Insertion Sort
  - Insertion chooses which element to insert using a gap of 1
  - Shell sort starts out using larger gap value
  - As the alogorithm progresses, gap value is reduced
  - Last gap value is 1, at this point it is equivalent to insertion sort 
  - Algorithm does preliminary works using gap value greater than 1 and then it performs insertion sort
  - By the time we get to insertion sort array would be partialy sorted hence it takes less time.
  
Performance:
  - In-place algorithm, logical partition of array is done. Extra memory is not required for partition.
  - Time Complexity - Depends on the gap choosen. Worst case - O(n^2)
  - It requires less shifting
  - Unstable algorithm
  
Merge Sort
  - Divide and Conquer Algorithm
  - Recursive algorithm
  - Two Phases: Splitting and Merging
  - Splitting is logical, New arrays are not created. Splitting leads to faster sorting during merging.
  - Splitting Phase: 
    + Start with unsorted array, divide it into 2 arrays left array and right array.
    + Split the left and right arrays again.
    + Keep splitting until all arrays have one element each.
  - Merging Phase:
    + Merge left and right sub arrays into sorted array.
    + After first merge we will have a bunch of 2 element sorted array.
    + Then merge these sorted arrays to end up with bunch of 4 element sorted array.
    + Keep merging untill a single sorted array is formed

Performancs:
  - Not inplace, Uses temporary arrays
  - O(logn) - base 2 . We're repeatedly dividing the arrays into half during splitting phase
  - Stable Algorithm
    
Quick Sort
  - Divide and Conquer Algorithm
  - Uses a pivot element to partition the elements of an array.
  - Elements less than pivot to left and elements greater than pivot to right.
  - So that, post partition pivot will be in its correct position
  - Elements in left and right side need not be in sorted order
  - Process is repeated for left and right sub-arrays as well.
  - End of it, every element would end of becoming a pivot and all elements would be in its correct position

Implementation:
  - Consider first element as the pivot element.
  - i -> to traverse array from left to right, initially points to start of array
  - j -> traverse array from right to left, initially points to end of array
  - Traverse the array from right to left by comparing each element to the pivot till we find an element that is less than the pivot.
  - Once an element is found at position(j), replace an element at position(i) with new element.
  - Now same element would be present in position i & j
  - Now traverse the array from left to right by comparing each element to the pivot till we find an element that is greater than the pivot
  - Once an element is found at position(i) replace element at position (j) with new element.
  - Repeat the process untill i is less than j.
  - Once i and j overlaps, replace the element at position j with pivot. Now pivoy element would be in its correct position in the array.
  - At the end of the iteration, elements to the left of the pivot would be less than pivot and elements to the right would be greater than pivot.
  
Performancs:
  - Not inplace, Uses temporary arrays
  - O(logn) - base 2 . We're repeatedly partition the arrays into half during splitting phase
  - Better than mergesort
  - Unstable Algorithm
  - Time complexity depends on pivot choosen

Counting Sort: 
  - Make assumptions about the data
  - Assumes that all values are within a range
  - Only works with non-negative discrete values(Can't work with strings, floats)
  
Performancs:
  - Not an in-place algorithm
  - O(n) - Can be achieved since we are making assumption
  
Implmentation:
  - Takes minimum value in the array and maximum value in the array as input
  - First create the count array to count each values in the array , size would be (max value - min value)+1, 
    to hold all values in the range
  - Traverse the input array and count how many occurence of each value exists.
  - Figure out the position in count array and increment the value.
  - countArray[inputArray[i] - min]++; -> Increment the count of particular element in the array.
  - Once countArray is completely created, Write the values to inputArray based on count Array values.
  - Use Loop 1 for traversing elements in the count array and 1 Inner Loop for traversing the repeated elements in the array.
  - Decrement the count values in inner loop

Radix Sort:
  - Makes assumption about the data it is sorting
  - Assumes all the values has same radix and width.
  - Radix -> range of values of digit or alphabet.
  - Ex: Binary Digit - 2(0 and 1), Decimal - 10(0-9), English alphabet - 26(A-Z)
  - Width -> Number of digits/letters
  - Ex: 1234 - 4(Since it has 4 digits), Hello - 5 (Since it has 5 letters)
  - Stable sorting has to be used to preserve the order of previous sorting.
  - Floating point number cannot be sorted using Radix Sort
  - Sort based on each individual letter or digit position starting from the rightmost digit.
  - Starts from digits at 1s position in first iteration.
  - Once digits in 1s position is sorted, digits in 10s position is sorted.
  - This continues till digits in all positions are sorted.
  - Stable Counting Sort is often used as Sort Algorithm since it is stable.

Stable Counting Sort:
  - Requires some extra steps to make it stable
  - Count the number as normal Counting Sort
  - Calculate where value should be written back to original array
  - Writing the values into the original array in backwards order ensures stability

Implementation of Stable Counting Sort
  - Create a temporary array that matches the length of array we are sorting
  - 1330 8792 1594 4725 4586 5729
  - Create the counting array as below for above mentioned values
  - 0 1 2 3 4 5 6 7 8 9
  - 0 0 2 1 0 0 0 0 1 2
  - Which indicates value 2 will be saved in index 0 and 1 and value 3 goes in index 2 and value 8 in index 3
  value 9 goes in index 4 and 5
  - Now we need to figure out the ranges
  - After creating the counting array now we need to adjust the count.
  - Instead just knowing the count, we need to know how many values have specific digit or less.
  - 0 1 2 3 4 5 6 7 8 9
  - 0 0 2 3 3 3 3 3 4 6
  - Indicates we have 0 values with 0 or less, 0 with 1 or less, 2 with 2 or less so on
  - Initialize the temp array.
  - int[] temp = new int[n];
  - Traverse the array backwards from right to left
  - for(int k=n-1;k>=0;k--){
      temp[--countArray[getDigit(position,input[k],radix)]] = input[k];
    }
    
  - When k=5,
  - Get the digit of particular width
  - (value/Math.pow(10,width))%radix
  - countArray[getDigit(...)] = countArray[2] for 5729. 
  - Since prefix subtract 1 from countArray countArray[2] = 1
  - Assign input[k] = 5729 to temp[1]
  - Temp Array: 0 5729 0 0 0 0
  - 0 1 2 3 4 5 6 7 8 9
  - 0 0 1 3 3 3 3 3 4 6
  - Rightmost value is written first, this gives stability
  
  - When k=4,
  - countArray[getDigit(...)] = countArray[8] for 4586. 
  - Since prefix subtract 1 from countArray countArray[8] = 3
  - Assign input[k] = 4586 to temp[3]
  - Temp Array: 0 5729 0 4586 0 0
  - 0 1 2 3 4 5 6 7 8 9
  - 0 0 1 3 3 3 3 3 3 6
  
  - When k=3,
  - countArray[getDigit(...)] = countArray[2] for 4725. 
  - Since prefix subtract 1 from countArray countArray[2] = 0
  - Assign input[k] = 4725 to temp[0]
  - Temp Array: 4725 5729 0 4586 0 0
  - 0 1 2 3 4 5 6 7 8 9
  - 0 0 0 3 3 3 3 3 3 6
  
  - When k=2,
  - countArray[getDigit(...)] = countArray[9] for 1594. 
  - Since prefix subtract 1 from countArray countArray[9] = 5
  - Assign input[k] = 1594 to temp[5]
  - Temp Array: 4725 5729 0 4586 0 1594
  - 0 1 2 3 4 5 6 7 8 9
  - 0 0 0 3 3 3 3 3 3 5
 
  - When k=1,
  - countArray[getDigit(...)] = countArray[9] for 8792. 
  - Since prefix subtract 1 from countArray countArray[9] = 4
  - Assign input[k] = 8792 to temp[4]
  - Temp Array: 4725 5729 0 4586 8792 1594
  - 0 1 2 3 4 5 6 7 8 9
  - 0 0 0 3 3 3 3 3 3 4
  
  - When k=0,
  - countArray[getDigit(...)] = countArray[3] for 1330. 
  - Since prefix subtract 1 from countArray countArray[3] = 2
  - Assign input[k] = 1330 to temp[2]
  - Temp Array: 4725 5729 1330 4586 8792 1594
  - 0 1 2 3 4 5 6 7 8 9
  - 0 0 0 2 3 3 3 3 3 4
  
  - Similar implementation can be used for sorting String array
  - getDigit method has to altered to get character from a String
  - str.charAt(position) - 'a'
  
 
Performancs:
  - O(n) - Can be achieved since we are making assumption
  - Slower than O(nLogn) because of the overhead involved
  - In-place depends on the sort alorithm
  - Stable algorithm

