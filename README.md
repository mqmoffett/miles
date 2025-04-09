from get_word import get_word              
from score import get_point_value             


def spelling_bee():
  letters_input = input("Welcome to Spelling Bee! Enter your 7 letters, separated by commas:")
  letters = letters_input.split(",")
  while True:
    required_letter = input(f"Which of these 7 letters {letters} will be your required letter?")
    if required_letter in letters:
      break
    else:
      print(f"{required_letter} is not an available letter. Please choose from the following: {letters}")
  used_words = []
  total_score = 0
  while True:
    word = get_word(letters, required_letter, used_words)
    if word == "END":
      break
    points = get_point_value(word, letters)
    total_score += points
    used_words.append(word)
  print(f"Your final score is {total_score}")

spelling_bee() 
