
import random
somewords = {"apple", "banana", "mango", "strawberry", "orange", "grape", "pineapple", "apricot", "lemon", "coconut", "watermelon","cherry", "papaya", "berry", "peach", "lychee", "muskmelon"}

words = random.choice(list(somewords))

total_chances = 5

gussed_words = "-"*len(words)
print("Guess the Words. Hint:-Words is a fruit")

while total_chances!= 0:
    
    print(gussed_words)
    
    letter = input("Enter a letter:").lower()
    
    if letter in words:
        for index in range(len(words)):
            if words[index] == letter:
                gussed_words = gussed_words[:index]+letter+gussed_words[index+1:]
        if gussed_words == words:
            print("Congratulations. You Won!!")
            break
    else:
        total_chances -= 1
        print("Incorrect_guess")
        print("Total chances remaining are ",total_chances)
        print("")
        
else:
    print("Game Over..")
    print("You Lose")
print("The Correct Word is", words)
