#include <stdio.h>
#include <stdlib.h>
// Hebda Patryk 11A1 P02

void gen_wektor(int n, double PH[n])
{
    for(int i=0;i<n;i++)
    {
        PH[i]=1+rand()%20;
    }
}

void print_wektor(int n, double PH[])
{
    for(int i=0;i<n;i++)
    {
        printf("%.1f  ",PH[i]);
    }
    printf("\n\n");
}

void max_wektor(int n,double PH[n],double *max)
{
    for(int i=0;i<n;i++)
    {
        if(PH[i]>*max && i%2==0)
        {
            *max=PH[i];
        }
    }
    printf("Maximum to: %f\n",*max);

}

void min_wektor(int n,double PH[n],double *min)
{
     for(int i=0;i<n;i++)
    {
        if(PH[i]<*min && i%3==0)
        {
            *min=PH[i];
        }
    }
        printf("Minimum to: %f\n",*min);
}

void wektor_A(int n,double A[n], double PH[n],double *max, double *min)
{
    for(int i=0;i<n;i++)
    {
        A[i]=PH[i]*(*max-*min);
    }
}

int main()
{
    int n;
    double max,min;

    printf("Podaj n:");
    scanf("%i",&n);

    double PH[n];
    double A[n];

    gen_wektor(n,PH);

    printf("PH:\n");
    print_wektor(n,PH);

    max=PH[0];
    min=PH[0];

    double *maksimum=&max,*minimum=&min;

    max_wektor(n,PH,maksimum);

    min_wektor(n,PH,minimum);

    wektor_A(n,A,PH,maksimum,minimum);

    printf("\nA: \n");
    print_wektor(n,A);

    printf("Patryk Hebda 11A1 P02\n");


    return 0;
}
