"""
Create a program that will play the 'cows and bulls' game
Randomly generate a 4 digit number. Ask to guess number
Every digit guessed in the correct place is a cow
Every digit the user guessed correctly but in the wrong place is a bull
Game is over when the correct number is guessed
Keep track of how many guesses
"""
import random

print('Welcome to the Cows and Bulls Game!')
answer = str(random.randint(1,9999))
answer = [int(i) for i in answer]
guess = None
tries = 0

while guess != answer:
    cow = 0
    bull = 0
    guess = input('Enter a 4 digit number: ')
    guess = [int(i) for i in guess]

    if len(guess) != len(answer):
        print('Guess must be 4 digits!\n')
        guess = input('Enter a 4 digit number: ')
        guess = [int(i) for i in guess]
    for i in range(len(answer)):
        if answer[i] == guess[i]:
            cow += 1
            bull -= 1
    for i in guess:
        if i in answer:
            bull += 1
    if guess == answer:
        print('Correct')
        print('Took {} tries'.format(tries))

    tries += 1
    print('You got Cows: {} and Bulls: {} \n'.format(cow, bull))
