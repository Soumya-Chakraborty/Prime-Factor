# A positive integer is entered through the keyboard, write a program to obtain the prime  factors of the number. Modify the function suitably to obtain the prime factors recursively
#include <stdio.h> // This line includes the standard input/output library, which allows us to use functions like printf and scanf

// A recursive function to find the prime factors of a number

void primeFactors(int n) // This line defines a function named primeFactors that takes an integer parameter n and returns nothing (void)

{

    // Base case: n is 1, nothing to do
    
    if (n == 1) // This line checks if n is equal to 1, which means we have reached the end of the recursion
        return; // This line exits the function without doing anything
    
    // Find the smallest prime factor of n
    for (int i = 2; i <= n; i++) // This line starts a loop from i = 2 to i = n, incrementing i by 1 each time
    {
        // If i is a prime factor of n, print it and divide n by i
        if (n % i == 0) // This line checks if i divides n evenly, which means i is a factor of n
        {
            printf("%d ", i); // This line prints i followed by a space
            n = n / i; // This line updates n by dividing it by i
            break; // This line breaks out of the loop, since we only need the smallest prime factor
        }
    }
    
    // Recursively find the prime factors of the reduced n
    
    
    primeFactors(n); // This line calls the same function with the updated value of n, which is smaller than before
}

// A main function to test the program

int main() // This line defines the main function that runs when the program starts
{
   
    int num; // This line declares an integer variable named num
    
    // Input a positive integer from the keyboard
    
    printf("Enter a positive integer: "); // This line prints a message to prompt the user for input
    
    scanf("%d", &num); // This line reads an integer from the keyboard and stores it in num
    
    // Print the prime factors of the number
    
    printf("The prime factors of %d are: ", num); // This line prints a message with the value of num
    
    primeFactors(num); // This line calls the primeFactors function with num as the argument
    
    return 0; // This line returns 0 from the main function, which indicates successful execution
}
