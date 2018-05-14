//Ahmed Hossam Hussien Idris
//Mostafa Anwar Sayed Mohammad
#include <iostream>
using namespace std;

int next[7];

bool Insert(char board[6][7], char player, int column)
{
    if (next[column]<0)
    {
        cout<<"Column is full"<<endl;
        return false;
    }
    board[next[column]][column]=player;
    next[column]--;
    return true;
}
char IsWinning(char board[6][7])
{
    for(int i=0; i<3; i++)
        for(int j=0; j<7; j++)
            if(board[i][j]==board[i+1][j]&&board[i+2][j]==board[i+3][j]&&board[i+1][j]==board[i+2][j]&&board[i][j]!=' ')
            {
                cout<<"Vertical ";
                return board[i][j];
            }

    for(int i=0; i<6; i++)
        for(int j=0; j<4; j++)
            if(board[i][j]==board[i][j+1]&&board[i][j+2]==board[i][j+3]&&board[i][j+1]==board[i][j+2]&&board[i][j]!=' ')
            {
                cout<<"Horizontal ";
                return board[i][j];
            }

    for(int i=0; i<3; i++)
        for(int j=0; j<4; j++)
            if(board[i][j]==board[i+1][j+1]&&board[i+2][j+2]==board[i+3][j+3]&&board[i+1][j+1]==board[i+2][j+2]&&board[i][j]!=' ')
            {
                cout<<"Diagonal ";
                return board[i][j];
            }

    for(int i=0; i<3; i++)
        for(int j=0; j<4; j++)
            if(board[i+3][j]==board[i+2][j+1]&&board[i+1][j+2]==board[i][j+3]&&board[i+2][j+1]==board[i+1][j+2]&&board[i+3][j]!=' ')
            {
                cout<<"Inverse Diagonal ";
                return board[i+3][j];
            }
    return ' ';

}

void Print(char board[6][7])
{
    for(int i=0; i<6; i++)
    {
        for(int j=0; j<7; j++)
        {
            cout<<"|"<<board[i][j]<<"|";
        }
        cout<<endl;
    }
}

int main()
{

    char board[6][7];
    int Column,counter=1;
    char Player,Check,Winner;
    bool a,b=true;

    for (int i=0; i<6; i++)
        for (int j=0; j<7; j++)
        {
            next[j]=5;
            board[i][j]=' ';
        }
    cout<<"Please enter starting player (X or O):";
    while(b)
    {
        cin>>Player;
        if(Player=='X'||Player=='O')
            b=false;
        else
            cout<<"Please enter X or O"<<endl;
    }
    while(Check!=Player)
    {
        cout<<"Please enter column for "<<Player<<" :";
        b=true;
        while(b)
        {
            cin>>Column;
            if(Column<7&&Column>=0)
                b=false;
            else
                cout<<"Please enter column from 0 to 6"<<endl;
        }
        a=Insert(board,Player,Column);
        if(a==true)
        {
            if(Player=='X')
                Player='O';
            else
                Player='X';
            counter++;
        }


        Print(board);

        Winner=IsWinning(board);
        if(Winner=='X'||Winner=='O')
            break;
        if(counter==42)
            break;
    }
    if(Winner=='X'||Winner=='O')
        cout<<"Winner is "<<Winner;
    else
        cout<<"No one won!!!!!";
}
