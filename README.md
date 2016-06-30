#include<stdio.h>
#include<stdlib.h>
int main()
{
	FILE *fp1;
	char *text;
	int len,i;
	fp1 = fopen("export.gpx","r");
	if((fp1 = fopen("export.gpx","r"))==0)
	{
		printf("文件不能正常打开");
		return (-1);
	}              
	fseek(fp1,0,SEEK_END);                 
	len=ftell(fp1);
	text=(char *)malloc(len);
	printf("length=%d\n",len);	
	fseek(fp1,0,0);
	fread(text,1,len,fp1);
	printf("%s\n",text);
	free(text);
	return 0;
}
