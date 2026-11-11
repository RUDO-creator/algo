#include <stdio.h>
#include <stdlib.h>
#include<time.h>
void TriSelection(int Tab[],int n){
    int i,j,PosMin,tmp;
    for(i=1;i<n-1;i++){
        PosMin=i;
        for(j=i+1;j<n;j++){
            if(Tab[j]<Tab[PosMin]){
                PosMin=j;
            }
        }
        if(PosMin!=i){
            tmp=Tab[PosMin];
            Tab[PosMin]=Tab[i];
            Tab[i]=tmp;
        }
    }
}
void TriInsertion(int Tab[],int n){
int i,j,tmp;
for(i=1;i<n;i++){
    tmp=Tab[i];
    j=i-1;
    while(j>0&&Tab[j]>tmp){
        Tab[j+1]=Tab[j];
        j=j-1;
    }
    Tab[j+1]=tmp;
}
}
void TriBulle(int Tab[],int n){
int i,j,tmp;
for(i=n;i<0;i--){
    for(j=2;j<i;j++){
        if(Tab[j-1]>Tab[j]){
            tmp=Tab[j-1];
            Tab[j-1]=Tab[j];
            Tab[j]=Tab[j-1];
        }
    }
}
}
int main()
{
int Tab1[1000],i;
clock_t START , END ;
float TIME;
int Tab2[1000],Tab3[1000],Tab4[1000],Tab5[1000];
for(i=0;i<1000;i++){
    Tab1[i]=rand();
    Tab2[i]=Tab1[i];
    Tab3[i]=Tab1[i];
    Tab4[i]=Tab1[i];
    Tab5[i]=Tab1[i];
}
START=clock();
TriSelection(Tab1,1000);
END=clock();
TIME=(float)(END-START)/CLOCKS_PER_SEC;
printf("Le temps d'execution pour la procedure TriSelection est :%f(s)",TIME);
START=clock();
TriInsertion(Tab2,1000);
END=clock();
TIME=(float)(END-START)/CLOCKS_PER_SEC;
printf("\nLe temps d'execution pour la procedure TriInsertion est :%f(s)",TIME);
START=clock();
TriBulle(Tab3,1000);
END=clock();
TIME=(float)(END-START)/CLOCKS_PER_SEC;
printf("\nLe temps d'execution pour la procedure TriBulle est :%f(s)",TIME);
}
