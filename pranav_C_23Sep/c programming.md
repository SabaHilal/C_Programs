# 1)To enter any string and count the number of alphabets digit and special character in it. 

````c
//to count the no. of alphabet, digit and other element in the string 
#include <stdio.h>
#include <string.h>
 
int main()
{
    char s[1000]; 
    int i,alphabets=0,digits=0,specialcharacters=0;
 
    printf("Enter  the string : ");
    gets(s);
     
    for(i=0;s[i];i++)  
    {
        if((s[i]>=65 && s[i]<=90)|| (s[i]>=97 && s[i]<=122) )
          alphabets++;
        else if(s[i]>=48 && s[i]<=57)
         digits++;
        else
         specialcharacters++;

 	}
 	
     
    printf("Alphabets = %d\n",alphabets);
    printf("Digits = %d\n",digits);
    printf("Special characters = %d", specialcharacters);
    

    return 0;
}
````

![image-20230923132408791](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923132408791.png)

## 2)To input a string and print it into reverse. 

````c
#include <stdio.h>
#include <string.h>
int main()
{
   char s[100]; 
   printf("Enter a string:");
   gets(s); 
   strrev(s);
   printf("The reverse of the string: %s\n", s);
   return 0;
}
````

![image-20230923132536608](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923132536608.png)

# 3)To input a string and count vowels and consonant 

````c
//to count the no of vowel and consonant in a string 

#include <stdio.h>
#include <string.h>
 
int main()
{
    char s[1000];  
    int i,vowels=0,consonants=0;
 
    printf("Enter  the string : ");
    gets(s);
     
    for(i=0;s[i];i++)  
    {
    	if((s[i]>=65 && s[i]<=90)|| (s[i]>=97 && s[i]<=122))
    	{
		
            if(s[i]=='a'|| s[i]=='e'||s[i]=='i'||s[i]=='o'||s[i]=='u'||s[i]=='A'||s[i]=='E'||s[i]=='I'||s[i]=='O' ||s[i]=='U')
		      vowels++;
            else
             consonants++;
        }

 	}
 	
     
    printf("vowels = %d\n",vowels);
    printf("consonants = %d\n",consonants);
    
    return 0;
}
````

![image-20230923132731321](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923132731321.png)

# 4)To enter a number and return square if even and cube if it is odd 

````c
// to give the square of the even no. and cube of the odd one 

#include<stdio.h>
int main()

{
    int n;

    printf("Please enter a number: ");
    scanf("%d", &n);

    if(n%2==0)
    {
        printf("%d", n*n);
    }
    else
    {
        printf("%d", n*n*n);
    }

    return 0;

}

````

![image-20230923132926824](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923132926824.png)

# 5)To find weather the string is palindrome or not 

````c
//to find out of the string is palinedrome or not 


#include <stdio.h>
#include <string.h>
 
int main()
{
    char s[1000];  
    int i,n,c=0;
 
    printf("Enter  the string : ");
    gets(s);
    n=strlen(s);

    for(i=0;i<n/2;i++)  
    {
    	if(s[i]==s[n-i-1])
    	c++;

 	}
 	if(c==i)
 	    printf("string is palindrome");
    else
        printf("string is not palindrome");

 	 
     
    return 0;
}
````

![image-20230923133118852](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923133118852.png)

# 6)To find all factor of a number 

````c
// to find out all factor of any no.
#include <stdio.h>
 
int main() {
    int n;
    printf("Enter a number : ");
    scanf("%d", &n);
     
    for (int i = 1; i <= n; ++i) {
        if (n % i == 0) {
            printf("%d  ", i);
        }
    }
    printf("\n");
}
````

![image-20230923133813905](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923133813905.png)

# 7)To convert decimal to binary 

````c
#include <stdio.h> 

void decToBinary(int n)
{
	int binaryNum[1000];

	int i = 0;
	while (n > 0) {

		binaryNum[i] = n % 2;
		n = n / 2;
		i++;
	}

	for (int j = i - 1; j >= 0; j--)
		printf("%d", binaryNum[j]);
}

int main()
{
	int n = 34;  // you can change the no. by changing the value of n 
	decToBinary(n);
	return 0;
}

````

![image-20230923133944249](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923133944249.png)

# 8)To find the largest no. in the array 

````c
#include <stdio.h>

int largest(int arr[], int n)
{
	int i;


	int max = arr[0];

	for (i = 1; i < n; i++)
		if (arr[i] > max)
			max = arr[i];

	return max;
}

int main()
{
	int arr[] = { 10, 324, 45, 90, 9808 };// you can change the array by making                                           //changes here 
    
	int n = sizeof(arr) / sizeof(arr[0]);
	printf("Largest in given array is %d", largest(arr, n));
	return 0;
}

````

![image-20230923134144912](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923134144912.png)

# 9)To sort the array .

````c
// to short the given array int hte program 


#include <stdio.h>

void swap(int* xp, int* yp)
{
	int temp = *xp;
	*xp = *yp;
	*yp = temp;
}

void selectionSort(int arr[], int n)
{
	int i, j, min_idx;

	for (i = 0; i < n - 1; i++) {

		min_idx = i;
		for (j = i + 1; j < n; j++)
			if (arr[j] < arr[min_idx])
				min_idx = j;

		swap(&arr[min_idx], &arr[i]);
	}
}

void printArray(int arr[], int size)
{
	int i;
	for (i = 0; i < size; i++)
		printf("%d ", arr[i]);
	printf("\n");
}


int main()
{
	int arr[] = { 22, 25, 41 , 1, 2, 99 };// you can change the array by making                                           //changes here
	int n = sizeof(arr) / sizeof(arr[0]);
	selectionSort(arr, n);
	printf("Sorted array: \n");
	printArray(arr, n);
	return 0;
}

````



​	![image-20230923134435266](C:\Users\test\AppData\Roaming\Typora\typora-user-images\image-20230923134435266.png)

