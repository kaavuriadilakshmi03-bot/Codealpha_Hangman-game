import random

words = ["python", "apple", "github", "laptop", "mouse"]

word = random.choice(words)

guessed_letters = []

attempts = 6

print("Welcome to Hangman Game")

while attempts > 0:

    display_word = ""

    for letter in word:
        if letter in guessed_letters:
            display_word += letter + " "
        else:
            display_word += "_ "

    print(display_word)

    if "_" not in display_word:
        print("You Won!")
        break

    guess = input("Enter a letter: ").lower()

    if guess in word:
        guessed_letters.append(guess)
        print("Correct Guess")
    else:
        attempts -= 1
        print("Wrong Guess")
        print("Attempts Left:", attempts)

if attempts == 0:
    print("Game Over")
    print("The word was:", word)
