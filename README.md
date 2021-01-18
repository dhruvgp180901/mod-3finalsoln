# LAB TASK 1: TIC TAC TOE

## LAYOUT OF THE PROJECT -

-> The project contains a root folder named **19074005-Dhruv-Gupta** which contains all the 4 python files corresponding to
    each solution of TIC-TAC-TOE -
    
    * Solution1.py - Algo 1
    
    * Solution2.py - Algo 2
    
    * Solution3.py - Algo 3
    
    * Solution4.py - Algo 4
 
 ->The folder also contains the **executable Jupyter Notebook** in which 4 different cells are there corresponding to each solution. 

## HOW TO RUN -

-> To run the project, open the **TIC_TAC_TOE_Solutions Jupyter Notebook** where each cell corresponds to some algo which is one of the solutions
    of the TIC-TAC-TOE game.
    
-> To execute any algo, just run the corresponding cell.

## HOW TO PLAY -

* **Player 1 always takes 'X' on the board while Player 2 takes 'O'.**
 
* **Board positions are referenced by integers in the range [1 - 9] sequentially-**
 
 
					     1 | 2 | 3 
					      --------
					     4 | 5 | 6
					      --------
					     7 | 8 | 9

1. At the start of the game, firstly you have to choose a number wich can be either 1 or 2 -
	
      => Player 1 i.e. the first turn will be yours.
      
      => Player 2 i.e. you will play after the first move by the opponent.

2. In each move of yours, you have to choose an integer from 1-9 denoting the cell where you want to mark -
	
	=> If that cell is already marked, then it will return a message i.e. "Invalid Move" and will ask you to choose another
       integer and the process will go on until you choose an empty cell.
       
	=> If that cell is empty, then it will mark and the game proceeds.
	

3. After each move, it will show the present state of board in which there will be three integers i.e "0,1,2" -
	
	=> empty cell is denoted by 0.
    
	=> If you have chosen 1, then 1 will denote your cells and 2 for opponents and else vice-versa.
	

4. **RESULT** => The game will continue until either one of the two players win or either its a tie.

## Details of the 4 Implemented Solutions - 

## SOLUTION - 1 =>

## Algorithm -

-> It consists of a movestates table which has all the 3^9 possible states of the board.

-> You have to veiw the board as a base 3(ternary) number, convert it to decimal number, and then select the vector 
   taking decimal number to be index and convert the board into that vector as it will represent the next state.

## Comments -

-> In theory, it will be an optimal game and efficient in terms of time also but it is not practically feasible to
   store all the states as it will take a large amount of space.

-> It will require a lot of manpower as all the states have to predetermined manually and thus there is a huge
   prabability of errors.

-> If we want to extend the game to let say, 3 dimensions, then all the 3^27 states could not be stored.It is beyond 	computer's memory.

-> Thus, it is not a good AI solution.

## SOLUTION - 2 =>

## Algorithm -

-> It uses three integers to represent the board i.e. - 
		
    => '2' for blank or empty cell,
		
    => '3' for player 1
		
    => '5' for player 2.

-> The algo has three functons -

**Centre** - It checkes whether the centre or the middle cell is empty or not otherwise it returns any empty non-corner cell.

**Winn_poss** - Prior to every move, it checkes for both conditions by checking the product of each row, column, and
			diagonal and returns the number of that cell i.e.-
				a) You are able to win in this move - if you are player 1, then the product will be 18 (18 = 3 * 3 * 2) and if
				   you are player 2, then it will be 50(5 * 5 * 2).
				b) Opponent is able to win in this move - It does so by checking the product again.  

**Cell_state** - It finally makes the move and set the cell to 3 or 5 according to the player number.

## Comments -

-> Since we have to check so many conditions before every move, so it is a bit lesst efficient in terms of time.

-> It is a lot more space efficient as we do not have to store any states in it.

-> Since, the technique for playing is already decided for this dimension, so it can;t also be extented to larger
   dimensions but it is possible to change the technique according to conditions.

## SOLUTION - 3 =>

## Algorithm -

-> In this solution, we have changed the numbering of cells in such a way that it has become a magic square and the
   sum of each row, column and diagonal becomes 15.

			      Initial board    =>     Final Magic Square
				1 | 2 | 3                8 | 3 | 4 
				--------                 --------
				4 | 5 | 6      =>        1 | 5 | 9
				--------                 --------
				7 | 8 | 9                6 | 7 | 2

-> It is very similar to solution - 2 but here, we check the possibility of win by using the sum of magic square i.e.-
	
  -> It checks the possibility of win by storing the sum of all pairs of two numbers aready used bu each player
	   separately, and then subtracting them from 15 and if the number is between 1 and 9, that means it can make a winning move and returns that number.
	
  -> Else, it checks the possibility of winning of the opponent using the same technique. 

## Comments -

-> It is even a more efficient approach as for ech move, only a few cells have to be checked, so it becomes less
   time - consuming and more straight-forward technique.

-> It also helps us understanding the way humans solve problems and the way, computers do. Since, computer can look at
   only one situation at a time while humans are able to see multiples simultanoeusly, so we get a better understanding of the diffenrce in the approaches of both.


## SOLUTION - 4 =>

## Algorithm -

-> In order to decide the next move, it looks ahead at all the positions of the board resulting from the next
   move and assigns a score or rating according to it and we move on the number with the highest rating.

-> If there is a possibility of winning, then we assign it highest and move.

-> Else, we check the possibility of opponents moves and checks which one is worst for us by recursively calling
   the function and assume that if  the opponent moves on there, then what will be the scoe.

-> Finally, we move to the cell with the highest score.  

## Comments -

-> It is an unbeatable and one of the best among the AI solutions of tic-tac-toe.

-> The recursive calling and checking all the possibilites and assining the scores, all is done under the name of
   "minimax" algorithm.

-> It requires more time than any of the above algoithm as it has to recursively search a tree to check all the 
   possibilities.

-> It is best as it can be extended to handle much more complex games thnan tic-tac-toe.

-> For very small problems, it may be inefficient but it can be the solution for much more complex problems for which 
    all the other solutions will fail.

-> It can be made more efficient by using the knowledge of games like - if it can be made possible to search only a 
    subset of all possibilities by precomputing or storing some things or to search only for a limited time and getting
    the rest result by some static funtion.
