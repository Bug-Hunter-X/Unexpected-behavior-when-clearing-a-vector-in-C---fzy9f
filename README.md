# Unexpected Vector Clearing in C++

This repository demonstrates a common error when attempting to clear a `std::vector` in C++ by iterating and erasing elements. The code appears to intend to clear the vector, but due to the way `erase()` modifies iterators, it results in unexpected behavior and only partially clears the vector.  The solution provides a correct and efficient method to clear the vector.

## Bug Description
The bug lies in the loop that iterates through the vector and erases each element.  When `vec.erase(vec.begin() + i)` is called, the elements after the erased element are shifted.  However, the loop's index `i` doesn't adjust for this shift, causing elements to be skipped and the vector not being fully cleared.

## Solution
The solution uses a more efficient and safer method, utilizing `vec.clear()` to completely empty the vector.  This is the recommended approach for clearing a vector in C++. 