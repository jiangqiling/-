#include<stdio.h>
#include<string.h>
#include<stdlib.h>
struct Xinxi
{
	char guojia[100];
	int jinpai;
	int yinpai;
	int tongpai;
	int zongji;
};
void printXinxi(struct Xinxi xinxi)
{
	printf("%s\t%d\t%d\t%d\t%d\n",xinxi.guojia,xinxi.jinpai,xinxi.yinpai,xinxi.tongpai,xinxi.zongji);
}
void fillXinxi(struct Xinxi* xinxi,char str[])
{
	char guojia[100]={'\0'};/*国家*/
	int guojiaIndex=0;
	int sIndex=0;
	while(str[sIndex]!='\t') guojia[guojiaIndex++]=str[sIndex++];
	strcpy(xinxi->guojia,guojia);
	sIndex++;
	char jinpai[100]={'\0'};/*金牌*/
	int jinpaiIndex=0;
	while(str[sIndex]!='\t') jinpai[jinpaiIndex++]=str[sIndex++];
	xinxi->jinpai=atoi(jinpai);
	sIndex++;
	char yinpai[100]={'\0'};/*银牌*/
	int yinpaiIndex=0;
	while(str[sIndex]!='\t') yinpai[yinpaiIndex++]=str[sIndex++];
	xinxi->yinpai=atoi(yinpai);
	sIndex++;
	char tongpai[100]={'\0'};/*铜牌*/
	int tongpaiIndex=0;
	while(str[sIndex]!='\t') tongpai[tongpaiIndex++]=str[sIndex++];
	xinxi->tongpai=atoi(tongpai);
	sIndex++;
	char zongji[100]={'\0'};/*总计*/
	int zongjiIndex=0;
	while(str[sIndex]!='\t') zongji[zongjiIndex++]=str[sIndex++];
	xinxi->zongji=atoi(zongji);
}
void main()
{
	FILE* infp=fopen("C:/Users/Desktop/file.txt","r");
	if(infp==NULL)
	{
		printf("Eorror!");
	}
	char str[8][100];
	int isFirstLine=1,i=0,j;
	while(fgets(str[i],100,infp)!=NULL)
	{
		if(isFirstLine==1) isFirstLine=0;
		else i++;
	}
	fclose(infp);
	struct Xinxi xinxi[8];
	for(i=0;i<8;i++)/*输出原信息*/
	{
		fillXinxi(&xinxi[i],str[i]);
		printXinxi(xinxi[i]);
	}
	printf("\n");
	struct Xinxi max=xinxi[0],min=xinxi[0];
	for(i=1;i<8;i++)
	{
		if(xinxi[i].zongji>max.zongji) max=xinxi[i];
		if(xinxi[i].zongji<min.zongji) min=xinxi[i];
	}
	printXinxi(max);
	printXinxi(min);
	for(j=1;j<8;j++)
	{
		for(i=0;i<8-j;i++)
		{
			if(xinxi[i].jinpai<xinxi[i+1].jinpai)
			{
				char t=xinxi[i];
				xinxi[i]=xinxi[i+1];
				xinxi[i+1]=t;
			}
		}
	}
	for(i=0;i<8;i++)/*输出排序后信息*/
	{
		printXinxi(xinxi[i]);
	}
}
