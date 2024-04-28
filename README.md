# SpellingBeeSolver
Fun side project for engineering solutions to the NY Times Spelling Bee Puzzle!

## How It's Made:

**Tech used:** Python, Jupyter Notebook

Function Definitions:

1. **load_words()**:
This function loads a list of valid words from a file named words_alpha.txt. The words are read from the file, split into individual words, and then stored in a set. Using a set ensures that each word is unique and allows for faster membership testing.

2. **is_valid_word()**:
This function checks if a given word is valid for the puzzle. A word is considered valid if it includes the central letter and if all its letters are among the specified group of letters. This function is designed to ensure compliance with the Spelling Bee puzzle's rules.

3. **find_solutions()**:
This function uses the previously defined is_valid_word function to filter through a list of words (loaded via load_words) and find all the words that are valid according to the Spelling Bee puzzle's rules. It returns a list of these valid words.

*Example Usage and Output:*
The script loads the word list using load_words().
It defines a set of letters and a central letter, which can be changed according to the actual puzzle for that day.
It then finds all valid solutions using the find_solutions function and prints them.
The results are then sorted and written to a file called spelling_bee_answers.txt, where each word is on a new line.

*Sample Execution:*
The script is prepared to be used with an example set of letters 'roadipn' with 'n' as the central letter. It will find words such as "pardon" (if it exists in words_alpha.txt), which includes 'n' and uses only the letters from 'roadipn'.

## Optimizations

After some experimentation I swapped processing the list to have unique words for it's immediate conversion into a set to improve the efficiency of the membership tests, as sets naturally guarantee unique entries and are more performant than the list ETL process I had initially implemented.

## Lessons Learned:

Membership testing is more complex than I had anticipated. Although the provided code is simple, the underlying logic it took to create it is more complex. I learned that sets are more efficient for membership testing than lists, especially for large datasets. I also learned that finding a comprehensive list of valid english words is harder than it seems, as there are many edge cases and exceptions to consider with many words being invalid "junk words" from the perspective of the Spelling Bee puzzle.