# Can-A-Number-Be-Expressed-As-A-Sum-Of-Two-Prime-Numbers-C-Program

Number be expressed as a sum of two prime numbers in C
Here, we will discuss the program to check whether a number be expressed as a sum of two prime numbers in C. The program in C takes a positive integer or number which is required to be inserted by the user. The program further identifies whether that digit can be expressed as the sum of two prime numbers. If the inserted number can be expressed as sum of two prime numbers then, print the integer can be expressed as sum of two prime numbers as a result.

Number be expressed as a sum of two prime numbers in C
Theory
There are many theories which express numbers as a sum of two primes like Goldbach’s Conjecture which states that any even number greater than 2 can be expressed as a sum of two primes.

Prime number is a number which only have two divisors i.e. a number which can not be divided by any other number other than 1 or itself is a prime number.

Here we will check for all the numbers if they can be expressed as sum of two primes or not.

Algorithm
Take number as input in n
Initialize a variable flag as 0
Iterate using for loop from value of i between (2, n/2)
 For each iteration Call a function sum_of_two_primes for value of i is it returns 1
Call same function for value n-i and if it is also 1 then print i and n-i as answer increment the flag to 1
If flag is 0 print not possible
Create function sum_of_two_prime where check if passed number is prime return true else false
While loop in C
sum of two prime numbers
C code
Run
// C program to check whether a number can be expressed as a sum of two prime numbers

#include<stdio.h>
int sum_of_two_primes(int n);
int main()
{
    int n, i;

    printf("Insert the num: ");
    scanf("%d", &n);
    int flag = 0;
    for(i = 2; i <= n/2; ++i)
    {
        // Condition for i to be prime
        if(sum_of_two_primes(i) == 1)
        {
            if(sum_of_two_primes(n-i) == 1)
            {
                printf("%d can be expressed as the sum of %d and %d", n, i, n-i);
                flag = 1;
            }

        }
    }

    if(flag == 0)
        printf("%d cannot be expressed as the sum of two primes\n", n);
    return 0;
}

int sum_of_two_primes(int n)
{
    int i, isPrime = 1;
    for(i = 2; i <= n/2; ++i)
    {
       if(n % i == 0)
       {
          isPrime = 0;
          break;
       }
    }
    return isPrime;
}
Output
Insert the num: 15
15 can be expressed as the sum of 2 and 13
