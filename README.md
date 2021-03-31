# TicTacToe2
using System;
using System.Collections.Generic;
using System.Text;


namespace ConsoleApp1
{
    class TicTacToe
    {

        static void Main(string[] args)
        {
            PlayGame();
            Console.ReadKey();     
            
        }
        public static void PlayGame()
        {
            char player = 'X';
            char[,] board = new char[6, 6]; 
            Introduction();          
            Initialize(board);    
            bool gameEnd = false;
            int movesPlayed = 0;
            



            
            while (gameEnd == false)
            {
                Console.Clear();
                Print(board);//print het af voor de eerste keer

                Console.Write("Choose a row: ");
                int row = Convert.ToInt32(Console.ReadLine());
                Console.Write("Choose a colum: ");
                int col = Convert.ToInt32(Console.ReadLine());

                board[row, col] = player;

                

                //HORIZONTAL 
                if (player == board[0, 0] && player == board[0, 1] && player == board[0, 2] && player == board[0, 3] && player == board[0, 4] && player == board [0, 5])
                {
                    Console.WriteLine(player + " has won the game with a horizontal win!");
                    PlayGame();
                    break;                   
                }

                if (player == board[1, 0] && player == board[1, 1] && player == board[1, 2] && player == board[1,3] && player == board[1, 4] && player == board [1, 5])
                {
                    Console.WriteLine(player + " has won the game with a horizontal win!");
                    PlayGame();
                    break;
                }

                if (player == board[2, 0] && player == board[2, 1] && player == board[2, 2] && player == board[2, 3] && player == board[2, 4] && player == board[2, 5])
                {
                    Console.WriteLine(player + " has won the game with a horizontal win!");
                    PlayGame();
                    break;

                }



                //DIAGONAL
                if (player == board[0, 0] && player == board[1, 1] && player == board[2, 2] && player == board[3, 3] && player == board[4, 4] && player== board[5, 5] )
                {
                    Console.WriteLine(player + " has won the game with a diagonal win!");
                    PlayGame();
                    break;

                }

                if (player == board[5, 0] && player == board[4, 1] && player == board[3, 2] && player == board[2, 3] && player == board[1,4] && player == board[0, 5])
                {
                    Console.WriteLine(player + " has won the game with a diagonal win!");
                    PlayGame();
                    break;

                }

                //VERTICAAL
                if (player == board[0, 0] && player == board[1, 0] && player == board[2, 0] && player == board[3, 0] && player == board[4, 0] && player == board[5, 0])
                {
                    Console.WriteLine(player + " has won the game with a vertical win!");
                    PlayGame();
                    break;

                }

                if (player == board[0, 1] && player == board[1, 1] && player == board[2, 1] && player == board[3, 1] && player == board[4, 1] && player == board[5, 1])
                {
                    Console.WriteLine(player + " has won the game with a vertical win!");
                    PlayGame();
                    break;

                }

                if (player == board[0, 2] && player == board[1, 2] && player == board[2, 2] && player == board[3, 2] && player == board[4, 2] && player == board[5, 2])
                {
                    Console.WriteLine(player + " has won the game with a vertical win!");
                    PlayGame();
                    break;

                }

                movesPlayed = movesPlayed + 1;

                if (movesPlayed == 12)
                {
                    Console.WriteLine("DRAW");
                    break;

                }
                


                player = ChangeTurn(player);
            }



            static char ChangeTurn(char currentPlayer)
            {
                if (currentPlayer == 'X')
                {
                    return '0';
                }
                else
                {
                    return 'X';
                }
            }

            static void Initialize(char[,] board)
            {
                
                for (int row = 0; row < 6; row++)
                {
                    for (int col = 0; col < 6; col++)
                    {
                        board[row, col] = ' ';
                    }

                }
            }

            static void Print(char[,] board)
            {
                Console.WriteLine(" | 0 | 1 | 2 | 3 | 4 | 5 | ");
                
                for (int row = 0; row < 6; row++)
                {
                    Console.Write(row + "| ");
                    for (int col = 0; col < 6; col++)
                    {
                        Console.Write(board[row, col]);
                        Console.Write(" | ");
                    }
                    Console.WriteLine();
                    
                }
            }
        }
        public static void Introduction()
        {
            Console.ForegroundColor = ConsoleColor.Green;
            Console.WriteLine(".-----. _         .-----.             .-----.            ");
            Console.WriteLine("`-. .-':_;        `-. .-'             `-. .-'            ");
            Console.WriteLine("  : :  .-. .--.     : : .--.   .--.     : : .--.  .--.   ");
            Console.WriteLine("  : :  : :'  ..'    : :' .; ; '  ..'    : :' .; :' '_.'  ");
            Console.WriteLine("  :_;  :_;`.__.'    :_;`.__,_;`.__.'    :_;`.__.'`.__.'  ");
            Console.ResetColor();
            Console.WriteLine("\nWelcome to tic tac toe, press any key to begin");
            Console.ReadKey();
            Console.Clear();
            Console.ForegroundColor = ConsoleColor.Blue;

        }
    }
}
