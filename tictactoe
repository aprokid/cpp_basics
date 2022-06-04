#include <iostream>
#include <ctime>

using namespace std;

const char PLAYER_1 = 'O';
const char PLAYER_2 = 'X';
char board[3][3];
int winningstate[8][3][2] = {{{0, 0}, {0, 1}, {0, 2}},
                             {{1, 0}, {1, 1}, {1, 2}},
                             {{2, 0}, {2, 1}, {2, 2}},
                             {{0, 0}, {1, 0}, {2, 0}},
                             {{0, 1}, {1, 1}, {2, 1}},
                             {{0, 2}, {1, 2}, {2, 2}},
                             {{0, 0}, {1, 1}, {2, 2}},
                             {{2, 0}, {1, 1}, {0, 2}}
                            };


void initialise()
{
    for(int i=0; i<3; i++)
        for(int j=0; j<3; j++)
            board[i][j] = '-';
}

void display()
{
    for(int i=0; i<3; i++)
    {
        for(int j=0; j<3; j++)
            cout << board[i][j] << " ";
        cout << endl;
    }
    cout << endl;
}

void setvalue(int row, int col, char symbol)
{
    board[row][col] = symbol;
}

bool isfree(int row, int col)
{
    if(board[row][col] == '-')
        return true;
    else
        return false;
}

bool haswon(char symbol)
{
    int row = 0;
    int col = 0;
    bool match = false;
    for(int m=0; m<=7; m++)
    {
        for(int s=0; s<=2; s++)
        {
            row = winningstate[m][s][0];
            col = winningstate[m][s][1];
            if(board[row][col] == symbol)
                match = true;
            else
            {
                match = false;
                break;
            }
        }
        if(match == true)
            return true;
    }
    return false;
}

int main()
{
    srand(time(NULL));
    bool gameover = false;
    int row = 0;
    int col = 0;
    int count_  = 0;
    char player = PLAYER_1;


    initialise();
    display();


    while(!gameover)
    {
        do
        {
            row = rand() % 3;
            col = rand() % 3;
        }
        while(!(isfree(row, col)));

        setvalue(row, col, player);
        if(haswon(player))
        {
            if(player == PLAYER_1)
                cout << "player 1 has won" << endl;
            else
                cout << "player 2 has won" << endl;
            display();
            break;
        }

        if(player == PLAYER_1)
            player = PLAYER_2;
        else
            player = PLAYER_1;

        count_++;

        if(count_ == 9)
            gameover = true;
        display();
    }

    return 0;
}
