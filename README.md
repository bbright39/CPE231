# CPE231
# ten-to-two
#include<math.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
void main()
{
    int base_input,ten=10,two=2;
    char in_put[30],strbase;
    printf("Hello !\n");
    printf("Please Enter Base 2 or 10 to convert to another base (2 or 10) : ");
    scanf("%d",&base_input);
    if(base_input == 10);
    {
        printf("Please Enter int number : ");
        scanf("%s",&in_put);
        convert_tentotwo(base_input,two,in_put);
    }
}
void convert_tentotwo(int base_input,int two,char in_put[])
{
    int length_strbase,i,j,intin_put,k=0,n;
    char zero_1[] = "0",str64[64]="",str1[64],x2[10];
    length_strbase = strlen(in_put);
    intin_put = atoi(in_put);
    int x = intin_put;
    if (x<0)
    {
        x=x*(-1);
        n=n+1;
    }
    itoa(x,x2,10);
    int result_divide = x;
    int fraction[64],result_fraction[64],cout=0;
    do
    {
        fraction[cout] = result_divide % 2;
        result_divide = result_divide / 2;
        cout++;
    }while(result_divide > 0.5);
    j = cout;
    while(j>0)
    {
            result_fraction[k] = fraction[j-1];
            sprintf(&str1[k], "%d", result_fraction[k]);
            //printf("str1:%s\n",str1);
            j--;k++;
            //printf("check base result_fraction : %d\n", result_fraction[k-1]);
    }
    n = 64 - cout;
        for( i = 0; i<n ;i++)
        {
            str64[i]='0';
        }
        for ( j=0 ; j<cout+1 ;j++,i++)
        {
            str64[i]=str1[j];
        }
    if(intin_put>0)
        printf("base 2 in 64  : %s",str64);
    if (intin_put == 0)
    {
        printf("base-2 : \n");
        for( i = 0; i<64 ;i++)
        {
             printf("0");
        }
    }
    else if(intin_put<0)
    {
        for(i=0; i<strlen(str64);i++)
        {
            if(str64[i]=='0')
            {
                str64[i]='1';
            }
            else if(str64[i]=='1')
            {
                str64[i]='0';
            }
        }
        if(str64[63]=='0')
        {
            str64[63] = '1';
        }
        else
        {
            for(i=63;i>0;i--)
            {
                str64[i]='0';
                if(str64[i-1]=='0')
                {
                    str64[i-1]='1';
                    break;
                }
            }
        }
        printf("\nbase 2 in 64  : %s",str64);
    }
}




