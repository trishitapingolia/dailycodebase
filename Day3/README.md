# Day 3 -- The Hamming Distance Problem

The Hamming distance between two strings of equal length is the number of positions at which the corresponding symbols are different.

It measures the minimum number of substitutions required to change one string into the other or the minimum number of errors that could have transformed one string into the other.

Read more about Hamming Distance [here…](https://en.wikipedia.org/wiki/Hamming_distance)

**Question**- Given 2 strings, we will find the number of positions at which the corresponding characters are different.

![Hamming](./cover.png)

**Example**

```
The hamming distance between
- "karolin" and "kathrin" is 3
- "karolin" and "kerstin" is 3
- 1011101 and 1001001 is 2
- 2173896 and 2233796 is 3
```

## JavaScript Implementation

### [Solution](./JavaScript/hamming.js)

```js
function hammingDistance (str1, str2) {
    let size1 = str1.length,
      size2 = str2.length,
      distance = 0;

    // Check if the strings are of equal length
    if (size1 !== size2) {
        console.log ("The strings \"" + str1 + "\" and \"" + str2 + "\" do not have equal lengths");
        return -1;
    }

    // Check the different characters at corresponding positions
    for (let i=0; i<size1; i++) {
        if (str1[i] !== str2[i]) {
            distance++;
        }
    }

    // Print the result and return the hamming distance
    console.log(`The hamming distance between "${str1}" and "${str2}" is ${distance}`);
    return distance;
}

hammingDistance('karolin', 'kathrin');
hammingDistance('karolin', 'kerstin');
hammingDistance('1011101', '1001001');
hammingDistance('2173896', '2233796');
```

## Java Implementation

### [Solution](./Java/HammingDistance.java)

```java
import java.util.Scanner;

public class HammingDistance {
    public static void main (String[] args) {
        System.out.println("/* ===== The Hamming Distance Problem ===== */");

        // Input the strings
        Scanner input = new Scanner(System.in);
        System.out.print("Enter the first string: ");
        String str1 = input.next();
        System.out.print("Enter the second string: ");
        String str2 = input.next();

        // set distance equal to zero
        int distance = 0;

        // check whether the strings are equal
        if (str1.length() != str2.length()) {
            System.out.println("Wrong Input! \"" + str1 + "\" and \"" + str2 + "\" are not of equal length");
            System.exit(-1);
        }

        // Check the different characters at corresponding positions
        for (int i=0; i<str1.length(); i++) {
            if (str1.charAt(i) != str2.charAt(i)) {
                distance++;
            }
        }

        // Print the result and return the hamming distance
        System.out.println("The Hamming Distance between the strings \"" + str1 + "\" and \"" + str2 + "\" is = " + distance);
        System.exit(0);
    }
}
```

## C++ Implementation

### [hamming.cpp](./C++/hamming.cpp)

```cpp
/*
 * @author: aaditkamat
 * @date: 24/12/2018
 */
 #include<iostream>
 #include<string>
 
 using namespace std;
 
 int hammingDistance(string first_word, string second_word) {
     int count = 0;
     if (first_word.size() != second_word.size()) {
        return -1;
     }
     for (int i = 0; i < first_word.size(); i++) {
         if (first_word[i] != second_word[i]) {
             count++;
         }
     }
     return count;
 }
 
 int main() {
     string first_word, second_word;
     cout << "Enter the first word: ";
     cin >> first_word;
     cout << "Enter the second word: ";
     cin >> second_word;
     cout << "The hamming distance between " << first_word << " and " << second_word << " is: " << hammingDistance(first_word, second_word) << endl;
     return 0;
 }
```

## C Implementation

### [hamming.c](./C/hamming.c)

```c
/**
 * @author: Rajdeep Roy Chowdhury<rrajdeeproychowdhury@gmail.com>
 * @github: https://github.com/razdeep
 * @date: 24/12/2018
 */

#include <stdio.h>
#include <string.h>

int hammingDistance(const char *first_word, const char *second_word)
{
    int count = 0;
    if (strlen(first_word) != strlen(second_word))
    {
        return -1;
    }
    for (int i = 0; i < strlen(first_word); i++)
    {
        if (first_word[i] != second_word[i])
        {
            count++;
        }
    }
    return count;
}

int main()
{
    char first_word[100], second_word[100];
    printf("Enter the first word: ");
    scanf("%s", first_word);
    printf("Enter the second word: ");
    scanf("%s", second_word);
    printf("The hamming distance between %s and %s is: %d\n", first_word, second_word, hammingDistance(first_word, second_word));
    return 0;
}
```
## Why Hamming Distance?

The #1 reason for not being successful is inconsistency, and it is a common trend that people start something and on give up on the third day itself, and one of the major reasons behind that is that they find it difficult to continue. 
So, to keep everyone (who is following the DailyCodes challenge) consistent, I have decided to keep today's question very simple and straightforward.