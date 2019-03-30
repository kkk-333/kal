Question. Sudesh Sharma is a Linux expert who wants to have an online system where he can handle student queries. Since there can be multiple requests at any time he wishes to dedicate a fixed amount of time to every request so that everyone gets a fair share of his time. He will log into the system from 10am to 12am only. He wants to have separate requests queues for students and faculty. Implement a strategy for the same. The summary at the end of the session should include the total time he spent on handling queries and average query time.

#include<stdio.h>
#include<unistd.h>
#include<string.h>
int main()
{
FILE *fp,*fp1;
int burst[100];
char name[20][10],s;
int count=0;
int i=0;
printf("enter u r charac");
scanf("%c",&s);
if(s=='f')
{
fp=fopen("fill.txt","a");
for(i=0;i<2;i++)
{
printf("enter name \n");
scanf("%s",name[i]);
printf("enter burst time \n");
scanf("%d",&burst[i]);
fprintf(fp,"%s%d",name[i],burst[i]);
if(burst[i]==-1)
break;
}
while(count<5){
for(i=0;i<2;i++)
{
if(burst[i]>0)
burst[i]--;
else
burst[i+1]--;
count++;
if(count==5)
break;
}
}
for(i=0;i<2;i++){
printf("after updated %d\n",burst[i]);}
for(i=0;i<2;i++){
if(burst[i]==0)
printf("process completed %s",name[i]);
}
}
if(s=='s')
{
fp=fopen("fill1.txt","a");
for(i=0;i<2;i++)
{
printf("enter name \n");
scanf("%s",name[i]);
printf("enter burst time \n");
scanf("%d",&burst[i]);
fprintf(fp,"%s%d",name[i],burst[i]);
if(burst[i]==-1)
break;
}
while(count<5){
for(i=0;i<2;i++)
{
if(burst[i]>0)
burst[i]--;
else
burst[i+1]--;
count++;
if(count==5)
break;
}
}
for(i=0;i<2;i++){
printf("after updated %d\n",burst[i]);}
for(i=0;i<2;i++){
if(burst[i]==0)
printf("process completed %s",name[i]);
}
}
}
