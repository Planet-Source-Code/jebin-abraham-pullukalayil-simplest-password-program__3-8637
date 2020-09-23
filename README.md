<div align="center">

## simplest password program


</div>

### Description

simplest password program... displays "*" as each letter is typed... enable backspace... good efficient
 
### More Info
 
you just need to know what pointers are that's all for this program...


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jebin Abraham Pullukalayil](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jebin-abraham-pullukalayil.md)
**Level**          |Beginner
**User Rating**    |4.4 (22 globes from 5 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+, Borland C\+\+
**Category**       |[Strings](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/strings__3-26.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jebin-abraham-pullukalayil-simplest-password-program__3-8637/archive/master.zip)





### Source Code

```
/* the most simplest logic and most simplest password program that enables
  backspace character ... just need to know what pointer and basics of
  pointer arithematic
  that's all just that much...*/
#include <stdio.h>   //for puts()
#include <conio.h>   //for getch(), getche()..etc...
#include <iostream.h>  //for (cout,cin)
#include <string.h>  //for strcmp()
void p1()
{
   clrscr();              //display screen... of course...
   cout<<"\n ENter the password ";
}
/* Basic pecularity for good basic and simple password program is that the password
  that one is typing, should not come on the screen... and that's there in this program*/
char* pass()
{
   char* password, *sub;          //the password string and sub -> well i'll tell u later
   char ch;              //the character that yer gonna enter
   int n=0,m;
                    /*
                     n->keeps track of stars that are displayed
                     m->well... i'll tell u later...
                    */
   sub=password;
                    /*now in this statement we store the password's 0th location in sub
                     you will understand why i am doing this later...*/
   p1();
   int i=0;             // i-> keep track of password
   ch=getch();
                   /*
                    well i used getch() becoz it gets character
                    from the keyboard, does not echo to screen.
                    for example if the input is 'j' if you enter
                    'j' still the screen would appear blank...
                   */
   do
   {
     if (ch!='\b')
     {
       cout<<"*";
                   /*as soon as you enter a character you want a
                    star to be displayed. so thats the command...*/
       n++;           //no of stars is incremented
       *password=ch;      //ch stored in password
       i++;           //i increments
       password++;       //now password will point to next location
     }
                 /*now all this will only take place if
                  ch is not backspace '\b'*/
     /* now the question comes "WHAT SHOULD BE DONE IF THE CHARACTER ENTERRED IS BACKSPACE???"
       now for example your original password is "INDIA" and now you have accidently entered
       "INDD".
       so you have to delete the D there from the password and also you have to delete one star
       from the output..
       just follow the following simple steps
       (1) display the display screen once more.
       (2) decrement the password pointer... right now it will pointing to the next location after
         the second D. you want to overwrite the D. so you'll have to decrement password so
         that it points now to second D;
       (3) decrement n because you don't want the 4the star that has appeared.
       (4) now display n stars that is the computer will display 3 stars now...
     */
     else if (ch=='\b')
     {
       p1();
       if (password!=sub)
       {
         password--;
         i--;
         m=n; //m is simple variable that's used. i dont want to touch my n...
         n--;
         for (; m>1; m--)
            cout<<"*";   // displays the new no. of stars
       }
       /* this condition above is just a small correction factor required in the program...
         well for example if the if statement was not there, just imagine that the password
         was "INDIA" and you by mistake typed "PAKISTAN" now you use the backspace and delete...
         like that you delete pakistan after you delete pakistan you by miskatedly pressed backspace
         2 more times and then you enterred india...
         Now the password that is stored will be dia instead of india because location of password
         will get substracted to a position lower that it's intial position or 0th position so when we
         enter i and n it's will be stored some addreess that come before password and dia will be stored
         in the password... so we need to stop accepting the backspaces when we reach the intial position.
         Well the correct this factor this if statement is used...
         sub has already password's intial address so the condition will check whether password has
         reached the initial address(i.e. all letters deleted). If the position of password is not the
         intial positon(ie. no equal to sub's position) the only it will decrement and i will be substracted.
         other wise it'll proceed forward that's it...*/
     }
     ch=getch();      //same proceedure follows unless enter is encountered.
   }while(ch!='\r');
   *password='\0';       //last part of password is entered as null
   for (; i>0; i--)
     password--;      //BRINGING THE POINTER TO FIRST LOCATION
   return password;      //RETURN POINTER
}
void main()
{
   char* pa;
   pa=pass();        //RECIEVING THE PASSWORD
   int m, n,i;
   m=n=0;
   i=strlen(pa);
   cout<<"\n The password that you enterred just now is ";
   puts(pa);
   cout<<"\n It's of length "<<i;
   getche();
}
/* well u can use this program anywhere you want cause i agree with just one thing
**"A CANDLE DOES NOT LOSE ANYTHING WHILE LIGHTING ANOTHER CANDLE"**/
```

