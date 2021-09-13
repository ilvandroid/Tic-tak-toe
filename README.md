//
//  main.c
//  tic-tac_game
//
//  Created by SUNNY KUMAR GUPTA on 16/06/21.
//

#include<stdio.h>

//#include<conio.h>

void check(char,char);
char a[9]={'1','2','3','4','5','6','7','8','9'};
//clrscr()

void gameName()
{
//textcolor(BLUE);
printf("  \n\t\t\t TIC TAK TOE Game :-) " );
}
//scanf("%c",&a);
//fflush(stdin);
//scanf("%c",&b);
void show()
{
printf("\n\n\t\t\t|---|---|---|");
printf("\n\t\t\t| %c | %c | %c |",a[0],a[1],a[2]);
printf("\n\t\t\t|---|---|---|");
printf("\n\t\t\t| %c | %c | %c |",a[3],a[4],a[5]);
printf("\n\t\t\t|---|---|---|");
printf("\n\t\t\t| %c | %c | %c |",a[6],a[7],a[8]);
printf("\n\t\t\t|---|---|---|");
//textcolor(RED);
//cprintf(" \n\n\n\nThe Charecter Is    %c %c",a, b);
//getch();
 }
 void inputSymbol()
{
//textcolor(MAGENTA+BLINK);
printf("\n\n\tThe Player 1's Symbol Is 'X'  ");
//textcolor(YELLOW);
printf("\n \tThe Player 2's Symbol Is '0'  ");
}
/*void start()
{
char pa;
printf("/n Enter who will start the game :Player 1 or Player2 /n ");
scanf("%c",&pa);
} */
void start()
{
char pa;
printf("\n\n\tEnter who will start the game : playre 1 or player 2 \n  ");
scanf("%c", &pa);

}
 void play()
 {
 char p,s;
 printf("\n\nEnter position And Symbol for the Player  ");
 fflush(stdin);
 scanf("%c",&p);
  fflush(stdin);
  scanf("%c",&s);
  check(p,s);
 }
void check(char P, char S)
 {
int i;
for(i=0;i<=8;i++)
    {
if(a[i]==P)
{   a[i]=S;  }
     }
}
       // condition to win the game or draw
          int end()
          {
        if  ((a[0]=='x'&& a[1]=='x' && a[2]=='x') ||
             (a[0]=='x'&& a[3]=='x' && a[6]=='x') ||
             (a[0]=='x'&& a[4]=='x' && a[8]=='x'))
             return(100);
         else if((a[1]=='x'&& a[4]=='x' && a[7]=='x') ||
             (a[2]=='x'&& a[5]=='x' && a[8]=='x') ||
             (a[2]=='x'&& a[4]=='x' && a[6]=='x') ||
             (a[3]=='x'&& a[4]=='x' && a[5]=='x') ||
             (a[6]=='x'&& a[7]=='x' && a[8]=='x'))
             return(100);

         else if((a[0]=='0'&& a[1]=='0' && a[2]=='0') ||
              (a[0]=='0'&& a[3]=='0' && a[6]=='0') ||
              (a[0]=='0'&& a[4]=='0' && a[8]=='0'))
             return(200);
         else if((a[1]=='0'&& a[4]=='0' && a[7]=='0') ||
             (a[2]=='0'&& a[5]=='0' && a[8]=='0') ||
             (a[2]=='0'&& a[4]=='0' && a[6]=='0') ||
             (a[3]=='0'&& a[4]=='0' && a[5]=='0') ||
             (a[6]=='0'&& a[7]=='0' && a[8]=='0'))
             return(200);
          else
              return(300);
          }

int main()
{
//printf("TIC TAC TOE");
char re;
int k;
//clrscr();
labell:
gameName();
//clrscr();
show();
inputSymbol();
start();
play();
    label:
     show();
     play();
k= end();
//clrscr();
show();
if(k==100)
printf("\n\tThe Game is won by player 1  ");
else if(k==200)
printf("\n\tThe Game is won by player 2  ");
else{
printf("\nThe Match Is Draw  ");
  goto label;
}
printf("\n\n\nDo u want The game play continue!! Enter 'Y' for Yes And 'N' for NO  ");
fflush(stdin);
scanf("%c",&re);
if (re=='y'|| re=='Y')
{   //goto labell;
    a[0]='1';
    a[1]='2';
    a[2]='3';
    a[3]='4';
    a[4]='5';
    a[5]='6';
    a[6]='7';
    a[7]='8';
    a[8]='9';
      goto labell;

    }

}
