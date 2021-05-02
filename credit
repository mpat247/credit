#include <stdio.h>
#include <math.h>
#include <stdlib.h>

//American Express: AMEX 15 digits starts with 34 and 37
//Mastercard: MC 16 digits starts with 51 52 53 54 55
//VISA: 13 or 16 digits starts wtih 13 or 16

//formula is to multiply every other digit by 2, starting from the second last digit and moving right
//after add the digits together
//add that to the remaining digits of the number initially entered


int main(void)
{
    //variable for credit card number input
    int crdnum = 0;

    do
    {
        printf("What is your card number?\n");
        scanf("%d", &crdnum);
    }
    while (crdnum < 0);
    
    printf("Number: %d", crdnum);
    
    int count = 0;
    long long digits = crdnum;
    //counting number of digits
    while(digits > 0)  
    {  
        digits = digits/10;  
        count++;  
    }  

    //if the credit card does not have the following number of digits, INVALID will be printed
    if ((count != 13) && (count != 15) && (count != 16))
    {
        printf("\nINVALID\n");
    }

    //turn credit card number into an array of integers
    // Array terms 0 1 2 3 4 5 6 7 8 9  10 11 12 13 14 15
    // Human terms 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16
    
    int number[count];
    for (int i = count - 1; i >= 0; i--)
    {
        number[i] = crdnum % 10;
        crdnum = crdnum / 10;
    }

    //starting to implement the formula
    //from 2nd last digit, multiply each digit by 2 then add all digits up, add that to the remaining digits

    int digitsum = 0;

    for (int i = count - 2 ; i>= 0 ; i-=2)
    {
        int product;
        product = number[1] * 2;
        digitsum = product % 10;
        if (product > 9)
        {
            digitsum += product / 10;
        }
    }

    //sum every other number that was not used before
    int sumOther = 0;
    for (int i = count - 1; i >= 0; i-=2)
    {
        sumOther += number[i];
    }

    //summing both amounts - digitsum and sumOther
    int both = digitsum + sumOther;

    //Checking to see if the last digit of the sum is 0

    if (both % 10 != 0)
    {
        printf("INVALID\n");
        exit(1);
    }

    //check what type of card it is by the length of the digits
    //only works if error is INVALID is not outputted

    if (count == 13)
    {
        printf("VISA\n");
    }
    else if (count == 15)
    {
        printf("AMEX\n");
    }
    else if (count == 16)
    {
        if (number[0] = 5)
        {
            printf("MASTERCARD\n");
        }
        else 
        {
            printf("VISA\n");
        }
    }
    
    


    return 0;
}
