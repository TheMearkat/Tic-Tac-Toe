#I wrote this in jupiter notebook so this method is called. Otherwise it would need to be imported from os.

from IPython.display import clear_output
#function displays the game board. 
def display_board(board):
    clear_output()
    
    print(board[7] + "| " + board[8]  + " |" + board[9])
    print("-------")
    print(board[4] + "| " + board[5] + " |" + board[6])
    print("-------")
    print(board[1] + "| " + board[2] + " |" + board[3])
    
    pass
    
    #function lets a player choose to play with either X or O. Returns markers for both players.
    def player_input():
      choice = ''

      while choice != 'X' and choice != 'O':
          choice = input("Player 1, choose X or O: ")
          clear_output()

      player1 = choice

      if choice == 'X':
          player2 = 'O'
      else:
          player2 = 'X'
    
      return(player1, player2)
      
      #function will put the marker at the given position on the given game board
def place_marker(board, marker, position):
      board[position] = marker
      pass
      
      #function checks if the game has been won. Will return True if so False otherwise.
def win_check(board, mark):
    
    #horizontal checks
    if board[7]==board[8]==board[9]==mark:
        return True
    elif board[4]==board[5]==board[6]==mark:
        return True
    elif board[1]==board[2]==board[3]==mark:
        return True
        
    #vertical checks
    elif board[1]==board[4]==board[7]==mark:
        return True
    elif board[2]==board[5]==board[8]==mark:
        return True
    elif board[3]==board[6]==board[9]==mark:
        return True
        
    #diagonal checks
    elif board[1]==board[5]==board[9]==mark:
        return True
    elif board[3]==board[5]==board[7]==mark:
        return True
        
    return False
        
    pass      
 
 #function will randomly select a player to go first.
import random

def choose_first():
    player1 = random.randint(0,100)
    player2 = random.randint(0,100)
    
    if player1 > player2:
        return "Player 1"
    else:
        return "Player 2"
    pass    
   
   #function will check if a selected position is valid by being empty. 
def space_check(board, position):
    if board[position] == 'X' or board[position] == 'O':
        return False
    else:
        return True
    pass    

#function will check if the game board is full to determine if the game has stopped
def full_board_check(board):
    count = 0
    
    for num in range(1, len(board)):
        if board[num] == 'X' or board[num] == 'O':
                count +=1
                
    if count == 9:
        return True
    else:
        return False
    pass
    
   #function will allow the user to mark a space. Will check for input errors. implements the space_check function to ensure space is valid.  
def player_choice(board):
    choice = 'wrong'
    
    while choice.isdigit() == False:
        choice = input("Which square would you like to take: ")
        
        if choice.isdigit() == False:
            print("Sorry, you did not enter an integer. Please try again.")
        else:
            if space_check(board, int(choice))==True:
                return int(choice)
    pass    
    
    #function will allow the user to select whether or not they want to play again
def replay():
    choice = input("Do you want to play again? Yes or No: ")
          
    if choice == 'Yes' or choice == 'yes':
        return True
    else:
        return False
    
        
    pass    
  
  
  #This is the main game. 
    print('Welcome to Tic Tac Toe!')

while True:
#while True:
    # The game set up
    new_board = ["#",' ', ' ',' ', ' ', ' ', ' ', ' ', ' ', ' ']
    player1, player2 = player_input()
    first_go = choose_first()
    print( first_go + ' will go first!')
    #pass

    play_game = input("Are you ready to play? Yes or No?")
    
    if play_game.lower()[0] == 'y':
        game_on = True
    else:
        game_on = False
    
    while game_on:
        #Player 1 Turn
        if first_go == "Player 1":  
            display_board(new_board)
            
            position = player_choice(new_board)
            
            place_marker(new_board, player1, position)
            if win_check(new_board, player1) == True:
                display_board(new_board)
                print("Player 1 has won the game!")
                game_on = False
            else:
                if full_board_check(new_board)== True:
                    display_board(new_board)
                    print("It's a tie!")
                    break
                else:
                    first_go = 'Player 2'
            
                
        else:
            # Player2's turn.
            display_board(new_board)
            
            position = player_choice(new_board)
            
            place_marker(new_board, player2, position)
            if win_check(new_board, player2) == True:
                display_board(new_board)
                print("Player 2 has won the game!")
                
                game_on = False
            else:
                if full_board_check(new_board)== True:
                    display_board(new_board)
                    print("It's a tie!")
                    break
                else:
                    first_go = 'Player 1'
                    
    
    if not replay():
        break
    
    
    
