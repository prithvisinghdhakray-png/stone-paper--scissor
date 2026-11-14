# stone-paper--scissor
a simple stone paper scissor game using c 

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    int user, computer;

    srand(time(0));

    printf("STONE PAPER SCISSORS GAME\n");
    printf("-------------------------\n");

    printf("1. Stone\n");
    printf("2. Paper\n");
    printf("3. Scissors\n");

    printf("\nEnter your choice: ");
    scanf("%d", &user);

    computer = rand() % 3 + 1;

    printf("\nYou chose: ");
    
    switch(user)
    {
        case 1: printf("Stone\n"); break;
        case 2: printf("Paper\n"); break;
        case 3: printf("Scissors\n"); break;
        default:
            printf("Invalid choice!\n");
            return 0;
    }

    printf("Computer chose: ");

    switch(computer)
    {
        case 1: printf("Stone\n"); break;
        case 2: printf("Paper\n"); break;
        case 3: printf("Scissors\n"); break;
    }

    if(user == computer)
    {
        printf("\nMatch Draw!");
    }
    else if((user == 1 && computer == 3) ||
            (user == 2 && computer == 1) ||
            (user == 3 && computer == 2))
    {
        printf("\nYou Win!");
    }
    else
    {
        printf("\nComputer Wins!");
    }

    return 0;
}
