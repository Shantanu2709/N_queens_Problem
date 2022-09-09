//# N_queens_Problem
//To solve this problem we will use Backtracking technique...
//* - Function for that the queen is safe to sit or not
 static boolean isSafe(char board[][],int row,int col)
    {
        for(int i=row-1; i>=0; i--)
        {
            if(board[i][col]=='Q')
            {
                return false;
            }
        }
        for(int i=row-1,j=col-1; i>=0&&j>=0; i--,j--)
        {
            if(board[i][j]=='Q')
            {
                return false;
            }
        }
        for(int i=row-1,j=col+1; i>=0&&j< board.length; i--,j++)
        {
            if(board[i][j]=='Q')
            {
                return false;
            }
        }
        return true;
    }
 //2:-
    static boolean nQueens(char board[][], int row) {
        //Base case
       if(row== board.length)
       {
           //printBoard(board);
           count++;
           return true;
       }

        //recursive function
        for (int j = 0; j < board.length; j++)
        {
            if(isSafe(board,row,j)) {
                board[row][j] = 'Q';
                if(nQueens(board, row + 1))
                {
                    return true;
                }
                board[row][j] = '.';
            }
        }
           return false;
    }
