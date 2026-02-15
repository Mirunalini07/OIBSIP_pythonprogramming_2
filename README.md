# OIBSIP_pythonprogramming_2
A beginner-friendly Python application that generates secure and customizable random passwords using user-defined length and character types such as letters, numbers, and symbols.
import random

letters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"
numbers = "0123456789"
symbols = "!@#$%^&*()_+-=[]{}|;:,.<>?"

length = int(input("Enter password length: "))

if length <= 0:
    print("Password length must be greater than 0")
    exit()

use_letters = input("Include letters? (y/n): ")
use_numbers = input("Include numbers? (y/n): ")
use_symbols = input("Include symbols? (y/n): ")

characters = ""

if use_letters.lower() == "y":
    characters += letters
if use_numbers.lower() == "y":
    characters += numbers
if use_symbols.lower() == "y":
    characters += symbols

if characters == "":
    print("You must select at least one character type.")
    exit()

password = ""

for i in range(length):
    password += random.choice(characters)

print("Generated Password:", password)
