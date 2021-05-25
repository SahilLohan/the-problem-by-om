#include <stdio.h>

int main()
{
    int n,num;
    printf("enter the no. of digits you are going to enter:-\n");
    scanf("%d",&n);
    printf("enter your number now\n");
    scanf("%d",&num);
    
    // i am storing every digit of number in array 
    int arr[n+1],h=1;
    for(int i=n-1;i>=0;i--)
    {
       
        int p;
        h=h*10;
        p=h/10;
        arr[i]=((num%h)-(num%p))/p;
        // printf("arr[%d] is %d\n",i,arr[i]);
        
    }
    // now i will swap the first and the last number  and print the number after swaping
    int temp;
    temp=arr[n-1];
    arr[n-1]=arr[0];
    arr[0]=temp;
    printf("\n\nThe number has become '");
    for(int i=0;i<n;i++)
    {
        printf("%d",arr[i]);
    }
    printf("' now");
    
    
    // now i will check if the entered number is palindrome or not
    
    for(int i=0;i<(n-1);i++)
    {
        if(arr[i]!=arr[n-i-1])
        {
            printf("\n\nthis number is not a palindrome");
            break;
        }
        if(i==n-2)
        {
            printf("\n\nthis number is a palindrome");
            break;
        }
    }
    return 0;
}
