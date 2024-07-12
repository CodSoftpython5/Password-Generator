# Password-Generator
#A password generator using Python allowing users to specify the length of password
import random
import array

Numbers = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']
Lowercase_letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h',
                    'i', 'j', 'k', 'm', 'n', 'o', 'p', 'q',
                    'r', 's', 't', 'u', 'v', 'w', 'x', 'y','z']
Uppercase_letters = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H',
                    'I', 'J', 'K', 'M', 'N', 'O', 'P', 'Q',
                    'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']
Symbols = ['@', '#', '$', '%', '=', ':', '?', '.', '/', '|', '~', '>',
           '*', '(', ')', '<']

Max_len = int(input("Enter maximum length of password: "))

Final_list = Numbers + Lowercase_letters + Uppercase_letters + Symbols

digit = random.choice(Numbers)
lower = random.choice(Lowercase_letters)
upper = random.choice(Uppercase_letters)
symbol = random.choice(Symbols)

password = digit + upper + lower + symbol

if Max_len < 4:
    print("Password length should not be less than 4 characters.")
else:
    for _ in range(Max_len - 4):
        password += random.choice(Final_list)

    pass_list = array.array('u', password)
    random.shuffle(pass_list)

    final_password = "".join(pass_list)
    print(final_password)



