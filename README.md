# Text-Adventure-Game---Monsters Inc.

def play_again():
    while True:
        print("Do you want to play again? (y or n)")
        # convert the players input to lower_case
        answer = input(">"). lower()

        if "y" in answer:  
            game()
        elif "n" in answer:
            print("Thank you for playing Monsters University!")
            break
        else:
            print("Invalid input, please enter y or n.")
        
# game_over function 
def game_over():
    print("Game Over, Better luck next time!")
    play_again()

# winner of the game
def win_game():
    print("You are a winner! You know your characters at Monsters University!")   

    
def movie_question():
    print(f'Welcome to your final stage of training. Let see if you know your partners from Monsters University! You ready to start!')
    input()


def sullys_room():
            print ("\nYou are in a room with Sully and a sleepy boy to scare.!")
            print ("Behind Sully, there is another door.")
            print ("What would you do? (1 or 2)")
            print ("1). Go scare the boy to be at the top of the scare list.")
            print ("2). Or go back out and say you are unscareable.")

def mikes_room():
            print ("\nYou have now entered a room where Mike\'s sleeping!")
            print ("Behind Mike, there is another door.")
            print ("What would you do? (1 or 2)")
            print ("1). Go and scare Sully so he can never sleep again.")
            print ("2). Or go back, and kill the monster to show your strength! ")

def boos_room(): 
            print ("\nYou have now entered a room where Boo is sleeping!")
            print ("Behind Boo, there is another door.")
            print ("What would you do? (1 or 2)")
            print ("1). Forget about scaring for the rest of your life and take care of Boo. ")
            print ("2). Or go back to scaring children as your full-time job! ")

def randalls_room():
            print ("\nYou have now entered a room where Randall is the scarer!")
            print ("Behind Randall, there is another door.")
            print ("What would you do? (1 or 2)")
            print ("1). Leave the room and never come back because Randall will beat you no matter what")
            print ("2). Or go back and fight for your spot in Monsters University!")
def question_sullys():
        sullys_room()
        try:
            answer = input(">")

            if answer =="1":
                print ("Nice, you're the top scarer of Monster University!")
                question_mikes()
            elif answer == "2":
                print("You're not the top scarer! Better luck next time partner!")
                game_over()
            else: 
                raise ValueError("Invalid entry, please enter 1 or 2!")
        except ValueError as e:
            print(str(e))
            question_sullys()
        
def question_mikes():
        mikes_room()
        try:
            answer = input(">")

            if answer =="1":
                    print("Good luck next time kid!")
                    question_sullys()
            elif answer == "2":
                    print ("Nice, you are the best scarer at Monster\'s University!")
                    question_boos()
            else: 
                    raise ValueError("Go learn how to count!")
        except ValueError as e:
            print(str(e))
            boos_room()
def question_boos():
        boos_room()
        try:
            answer = input(">")

            if answer =="1":
                    print ("Nice, you have a sweet spot for children'!")
                    question_randalls()
            elif answer == "2":
                    print("Good luck next time Sully!")
                    question_mikes()
            else: 
                    raise ValueError("Invalid entry, please enter 1 or 2!")
        except ValueError as e:
            print(str(e))
            randalls_room()
    
def question_randalls():
        randalls_room()
        try:
            answer = input(">")

            if answer =="1":
                    print("Better luck next time! ")
                    question_boos()
            elif answer == "2":
                    print ("Awesome! You know you deserve to be at Monsters University'!")
            else: 
                    raise ValueError("Type the correct number!")
        except ValueError as e:
            print(str(e))
            game_over()

def game():
    #introducing the game
    name= input(f'Enter your First name! (<Press Enter to Continue>)').capitalize()
    print(f' Greetings {name}. Welcome to your adventure to Monsters University!')
    print(f' You have been selected to join our team of top-performing monsters.')
    print(f' Your mission is to decide which method of scaring is correct at this University.')
    print(f' You must be careful, if you insert the wrong answer, you will end the game or return to the previous question.')
    print(f' If you insert the wrong answer, you will end the game or return to the previous question.')
    print(f' The goal at the very end is to test your knowledge on the movie Monsters Inc. All responses must be in lowercase.')
    print(f' Are you ready to join the ranks of Sully, Mike, Boo and Randall!')
    print(f'Let\'s get started! (<Press Enter to Continue>)')
    input()


    start = input ('Would you like to start the game yes or no!')
    if start == 'yes':
        print("Great let\'s start this adventure together!")
        question_sullys()
    else:
        print('Well seems like you did not want to adventure in Monsters University')
        game_over();


  # question for the last stage of the game  
        movie_question()
    for index in range(3): 
        s = ("Who said this line from Monsters Inc. 'Give it a rest, will ya, butterball?'")
        m= ("Who said this line 'You and I are a team. Nothing is more important than our friendship!'" )
        b= ("Who said this line, 'Kitty'")
        lst_Prompt = [s,m,b,]
        lst_Answer = ["sully","mike","boo"]
        try:
            print(lst_Prompt[index])
            v = input("Answer: ")
            if v!=lst_Answer[index]:
                game_over()
            win_game()
        except Exception as e:
            print("An error occured:", e)
            
        
# function to ask play again or not
game()
