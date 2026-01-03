# mini-project-in-c
Modern Periodic Table (C Program)

# Modern Periodic Table (C Program)

## Description
This project is a simple **console-based Modern Periodic Table** written in C.  
It allows the user to interact with a menu-driven interface to view information about chemical elements by atomic number. Currently, the program supports displaying detailed data for the element Hydrogen.

## Features
- Welcome screen with a clear main menu.
- Option to:
  - Enter `1` to learn about an element.
  - Enter `2` to close the periodic table.
- Search element details by atomic number (currently supports atomic number `1` for Hydrogen).
- Displays:
  - Name  
  - Symbol  
  - Atomic Number  
  - Electronic Configuration  
  - Discoverer  
  - Charge  
- Exit confirmation flow with options to continue exploring elements.

## How It Works
1. On running the program, you are shown:
   - `1` → Know about an element  
   - `2` → Close the periodic table  
2. If you choose `1`:
   - You are asked to press `3` to search by atomic number.
   - Then you enter the atomic number (e.g., `1` for Hydrogen).
   - The program prints the details of Hydrogen if `a == 1`.
3. If you choose `2`:
   - You are asked if you want to exit:
     - `6` → Yes  
     - `7` → No  
   - If `6` (Yes) is chosen:
     - You are again asked for confirmation:
       - `4` → Confirm close  
       - `5` → Do not close and continue  
   - If you choose not to close, the program lets you continue to enter an atomic number and see element details.

## Code
'''text
//modern periodic table	

#include<stdio.h>

int main()
{
    int n;
    int m;
    int a;
    int Exit;
    int Exi;
     
    printf("Welcome to Modern Periodic Table\n\n");
    
    printf(">Enter 1 to know about an element\n\n");
    printf(">Enter 2 to close the periodic table\n\n");
    
    printf("ENETR\n");
    scanf("%d",&n);
    
    if(n==1)
    {
        printf(">Press 3 to search the element by atomic number\n\n");
        
        printf("ENETR\n");
        scanf("%d",&m);
        
        if(m==3)
        {
            printf("Enter the atomic number of the element to be searched:");
            scanf("%d",&a);
            
            if(a==1)
            {
                printf("Nmae : Hydrogen\n");
                printf("Symbol : H\n");
                printf("Atomic Number : 1\n");
                printf("Electronic Configuration : 1s^1\n");
                printf("Discovered By : Henry Cavendish\n");
                printf("Charge : +1\n");
            }
        }
    }
    else if(n==2)
    {
        printf("Do you want to  exit?(yes/No)\n");
        printf("> Press 6 for Yes\n");
        printf("> Press 7 for No\n");
        
        printf("ENTER\n");
        scanf("%d",&Exit);
        
        if(Exit==6)
        {
            printf("Are you sure,you want  to close the periodic table?(Yes/No)\n");
            printf("> Press 4 for Yes\n");
            printf("> Press 5  for No\n");
            
            printf("ENTER\n");
            scanf("%d",&Exit);
            
            if(Exit==4)
            {
                printf("The periodic table has closed");
            }
            else if(Exit==5)
            {
                printf("Periodic table has not closed and you can continue to learn more about elements\n");
                printf("Enter the atomic number of the element to be searched :\n\n");
                printf("%d",&a);;
                
                if(a==1)
                {
                    printf("Nmae : Hydrogen\n");
                    printf("Symbol : H\n");
                    printf("Atomic Number : 1\n");
                    printf("Electronic Configuration : 1s^1\n");
                    printf("Discovered By : Henry Cavendish\n");
                    printf("Charge : +1\n"); 
                }
            }
        }
        else if(Exit==7)
        {
            printf("Periodic table has not closed and you can continue to learn more elements\n\n");
            
            printf("Enter the atomic number  of the element to be searched :");
            scanf("%d",&a);
            
            if(a==1)
            {
                printf("Nmae : Hydrogen\n");
                    printf("Symbol : H\n");
                    printf("Atomic Number : 1\n");
                    printf("Electronic Configuration : 1s^1\n");
                    printf("Discovered By : Henry Cavendish\n");
                    printf("Charge : +1\n"); 
            }
            
        }
    } 
}		

## Example Interaction
```text
Welcome to Modern Periodic Table

>Enter 1 to know about an element
>Enter 2 to close the periodic table
ENETR
1

>Press 3 to search the element by atomic number
ENETR
3
Enter the atomic number of the element to be searched: 1

Nmae : Hydrogen
Symbol : H
Atomic Number : 1
Electronic Configuration : 1s^1
Discovered By : Henry Cavendish
Charge : +1

 
