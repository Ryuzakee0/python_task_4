# python_task_4
# This is Task - 4 Rock, Pepar, Sessior Game

import random as rd

print('-----------------------------')
print("***** ROCK-PEPAR-SESSIOR GAME ...!")
print('-----------------------------')

name = input("Enter Your Name :")
user_score = 0
comp_score = 0

rounds = 1
while rounds <= 10:

    print("-------------------------------")
    print("**** SCORE BOARD ****")
    print(f"{name} Score : {user_score}")
    print(f"Computer Score : {comp_score}")
    print("-------------------------------")

    print()
    print(f"Round No. {rounds}")
    print('* * * * * * * ')
    print("1. Rock")
    print("2. Pepar")
    print("3. Sessior")
    print("4.Stop Game ..!")
    print()

    user_choice = ''
    option = int(input("Enter Choice :"))
    match (option):
        case 1:
            user_choice = "Rock"
        case 2:
            user_choice = "Pepar"
        case 3: 
            user_choice = "Sessior"
        case 4:
            break

    # Generating computer choice
    computer = ['Rock','Pepar','Sessior']
    comp_choice = rd.choice(computer)

    if len(user_choice) != 0:
        print('----------------------------------------')
        print(f'{name} Choice is : {user_choice}')
        print(f'Computer choice is : {comp_choice}')
        print()

        if user_choice == comp_choice:
            print("Game is DRAW / TIE ..!")
        elif user_choice == "Rock":
            if comp_choice == "Pepar":
                print("Computer Wins !")
                comp_score += 1
            elif comp_choice == "Sessior":
                print(f"{name} Win !")
                user_score += 1

        elif user_choice == "Pepar":
            if comp_choice == "Sessior":
                print("Computer Win !")
                comp_score += 1
            elif comp_choice == "Rock":
                print(f"{name} Win !")
                user_score += 1

        elif user_choice == "Sessior":
            if comp_choice == "Rock":
                print("Computer Win !")
                comp_score += 1
            elif comp_choice == "Pepar":
                print(f"{name} Win !")
                user_score += 1
    else:
        print("Invalid User choice ..!")

    print('---------------------')
    rounds += 1  # Updating rounds

print()
if user_score == comp_score:
    print("Game is Draw ..!")
elif user_score > comp_score:
    print(f"Congratulations {name} ! Your are Winner ...!")
elif user_score < comp_score:
    print(f"Computer WIN ..!")
    print("Better Luck Next Time ...!")
