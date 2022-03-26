#include<stdio.h>
int num[1001][1001];
int main()
{
	int M,N,i,j,k,a,sum[1000];
	char str[1001][20];
	scanf("%d",&M);
	for(i=1;i<=M;i++)
	{
		scanf("%s%d",str[i],&a);
		for(j=1;j<=M;j++)
		{
			if(j==a)
				scanf("%d",&num[i][j]);
		}
	}
	scanf("%d",&N);
	for(i=1;i<=N;i++)
	{
		scanf("%d",&sum[i]);
	}
	for(i=1;i<=N;i++)
	{
		for(j=1;j<=M;j++)
		{
			if(num[j][sum[i]]!=0)
			{
				k=j;
				break;
			}
		}
		printf("%s ",str[k]);
		printf("%d\n",num[k][sum[i]]);
	}
}
