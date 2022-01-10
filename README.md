# Guess_d_number

import random
#Number Guessing Game Objectives:
logo = """
 ██████  ██    ██ ███████ ███████ ███████     ████████ ██   ██ ███████     ███    ██ ██    ██ ███    ███ ██████  ███████ ██████  
██       ██    ██ ██      ██      ██             ██    ██   ██ ██          ████   ██ ██    ██ ████  ████ ██   ██ ██      ██   ██ 
██   ███ ██    ██ █████   ███████ ███████        ██    ███████ █████       ██ ██  ██ ██    ██ ██ ████ ██ ██████  █████   ██████  
██    ██ ██    ██ ██           ██      ██        ██    ██   ██ ██          ██  ██ ██ ██    ██ ██  ██  ██ ██   ██ ██      ██   ██ 
 ██████   ██████  ███████ ███████ ███████        ██    ██   ██ ███████     ██   ████  ██████  ██      ██ ██████  ███████ ██   ██ 
 """                                                                                   

print(logo)                                                                                                                                 

# Allow the player to submit a guess for a number between 1 and 100.
EASY_LEVEL = 10
HARD_LEVEL = 5

def game():
  #Make function to set difficulty.
  def difficulty_level():
    level_of_difficulty = input("Choose a difficulty. Type 'easy' or 'hard':\n").lower()
    game_chance = 0
    if level_of_difficulty == "easy":
     return EASY_LEVEL
    else:
      return HARD_LEVEL

  start = input('Welcome to the Number Guessing Game!')
  turns = difficulty_level()
  

  dealer = input ("I'm thinking of a number between 1 and 100.")
  answer = random.randint(1,100)
  print(answer)
  #Function to check user's guess against actual answer.
  def confirm_answer(guess,answer,turns):
   """checks answer against guess. Returns the number of turns remaining."""
   if guess > answer:
    print('Too high')
    return turns -1
   elif guess < answer :
    print ('Too low')
    return turns -1
   else :
      print(f"Your guess is right, the answer is {answer}")

  guess = 0

  while guess != answer:
    print(f'You have {turns} tries')
    guess = int(input("Guess the number: \n"))
    turns = confirm_answer(guess,answer,turns)
    if turns == 0:
      print('You are out on guesses, you lose')
      return
    elif guess != answer:
      print("Guess again.")

game()


    



# Check user's guess against actual answer. Print "Too high." or "Too low." depending on the user's answer. 
# If they got the answer correct, show the actual answer to the player.
# Track the number of turns remaining.
# If they run out of turns, provide feedback to the player. 
# Include two different difficulty levels (e.g., 10 guesses in easy mode, only 5 guesses in hard mode).
