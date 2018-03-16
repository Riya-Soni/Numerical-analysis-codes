# Numerical-analysis-codes
#include <stdio.h>
#include <conio.h>
#include <math.h>
float f(float x)
{
    return((x*x)-x-1);
}
void main()
{
    int i=1;
    float a=1,b=2,m,e=0.0001;
    //clrscr();
    //printf("Enter Value of a & b:\n");
    //scanf("%f%f",&a,&b);
    if((f(a)*f(b))>0)
    {
        printf("invalid interval");
    }
    else
    {
        m=(a+b)/2;
        while(fabs(f(m))>e)
        {
            printf("i=%d\t a=%f\t b=%f\t m=%f\t f(m)=%f\t f(a)*f(m)=%f\n",i,a,b,m,f(m),(f(a)*f(m)));
            if((f(a)*f(m))>0)
                a=m;
            else
                b=m;
            m=(a+b)/2;
            i++;
        }
        printf("Out of loop\n");
    }
    printf("i=%d\t a=%f\t b=%f\t m=%f\t f(m)=%f\t f(a)*f(m)=%f\t",i,a,b,m,f(m),(f(a)*f(m)));
    //getch();
}

//Regular false method

#include <stdio.h>
#include <math.h>
float f(float x)
{
    return((x*x)-x-1);
}
void main()
{
    int i=1;
    float a=1,b=2,m,e=0.0001;
    //clrscr();
    //printf("Enter Value of a & b:\n");
    //scanf("%f%f",&a,&b);
    if((f(a)*f(b))>0)
    {
        printf("invalid interval");
    }
    else
    {
        m=((a*f(b))-(b*f(a)))/(f(b)-f(a));
        while(fabs(f(m))>e)
        {
            printf("i=%d\t a=%f\t b=%f\t m=%f\t f(m)=%f\t f(a)*f(m)=%f\n",i,a,b,m,f(m),(f(a)*f(m)));
            if((f(a)*f(m))>0)
                a=m;
            else
                b=m;
            m=((a*f(b))-(b*f(a)))/(f(b)-f(a));
            i++;
        }
        printf("Out of loop\n");
    }
    printf("i=%d\t a=%f\t b=%f\t m=%f\t f(m)=%f\t f(a)*f(m)=%f\t",i,a,b,m,f(m),(f(a)*f(m)));
    //getch();
}
