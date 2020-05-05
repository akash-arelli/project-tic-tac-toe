# project-tic-tac-toe

#include <stdio.h>
char a[10]={'0','1','2','3','4','5','6','7','8','9'};
int check(char);
int v=0;
 int count=0;
int show()
{
    printf("\n\n\t\t\t---|---|---\n");
    printf("\t\t\t %c | %c | %c \n",a[1],a[2],a[3]);
     printf("\t\t\t---|---|---\n");
       printf("\t\t\t %c | %c | %c \n",a[4],a[5],a[6]);
      printf("\t\t\t---|---|---\n");
        printf("\t\t\t %c | %c | %c \n",a[7],a[8],a[9]);
       printf("\t\t\t---|---|---\n");
    return 0;
}
int input()
{
    printf("\nplayer 1 : symbol x\n");
    printf("player 2 : symbol 0\n");
    
    return 0;
}
int start()
{
     char pa;
    printf("who will start the game:player 1 or player 2\n");
    scanf("%c",&pa);
      
    return 0;
}
int play()
{
   
     printf("\nenter postion ");
    char p;
    scanf(" %c",&p);
    
    check(p);
    
    return 0;
    
}
int check(char p)
{
    
 
    int i;
    if(v==0)
    {for(i=1;i<=9;i++)
    {
        if(a[i]==p)
        {
            a[i]='x';
            v=1;
              count++;
            break;
        }
    }
    }
 else{   for(i=1;i<=9;i++)
    {
        if(a[i]==p)
        {
            a[i]='0';
              count++;
            v=0;
            break;
        }
    }
 }
    return 0;
}
int end()
{
    for(int i=1;i<=3;i++)
    {
        if(a[i]=='x'&&a[i+3]=='x'&&a[i+6]=='x')
        return 100;
        else if(a[i]=='0'&&a[i+3]=='0'&&a[i+6]=='0')
        return 200;
    }
    for(int i=1;i<=7;i=i+3)
    {
        if(a[i]=='x'&&a[i+1]=='x'&&a[i+2]=='x')
        return 100;
        else if(a[i]=='0'&&a[i+1]=='0'&&a[i+2]=='0')
        return 200;
    }
    
    if((a[1]=='x'&&a[5]=='x'&&a[9]=='x')||(a[3]=='x'&&a[5]=='x'&&a[7]=='x'))
    return 100;
    if((a[1]=='0'&&a[5]=='0'&&a[9]=='0')||(a[3]=='0'&&a[5]=='0'&&a[7]=='0'))
    return 200;
    
    return 300;
}
int main()
{
   
    int k;
    char l;
    label1:
    show();
    input();
    start();
    play();
    label:
    system("clear");
    show();
    play();
    k=end();
     system("clear");
     show();
    if(count<9)
    { if(k==100)
     printf("player 1 has won the game\n");
     else if(k==200)
      printf("player 2 has won the game\n");
    else
    goto label;
    }
    if(count==9&&k==300)
    {
        printf("\nDRAW\n");
        count=0;
    }
    else if(count==9)
    {
        if(k==100)
        printf("player 1 has won the game\n");
        else if(k==200)
         printf("player 2 has won the game\n");
    }
    
    
    printf("to play again press y\nto exit the game press e\n");
    scanf(" %c",&l);
    if(l=='y')
    {
       count=0;
        a[1]='1';
        a[2]='2';
        a[3]='3';
        a[4]='4';
        a[5]='5';
        a[6]='6';
        a[7]='7';
        a[8]='8';
        a[9]='9';
        goto label1;}
    else{
        system("clear");
    }
    return 0;
}


