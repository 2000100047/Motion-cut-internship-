import string
from collections import Counter

def main():
    text = input("Enter the text you want to analyze: ")
    total_words, unique_words, word_frequency = count_words(text)
    print(f"Total number of words: {total_words}")
    print(f"Number of unique words: {unique_words}")
    print("Word frequencies:")
    for word, frequency in word_frequency.items():
        print(f"{word}: {frequency}")

def count_words(text):
    # Convert to lowercase to ensure case-insensitivity
    text = text.lower()
    # Remove punctuation
    text = text.translate(str.maketrans('', '', string.punctuation))
    # Split the text into words
    words = text.split()
    # Count total words
    total_words = len(words)
    # Count unique words
    unique_words = len(set(words))
    # Count frequency of each word
    word_frequency = Counter(words)
    return total_words, unique_words, word_frequency

if __name__ == "__main__":
    main()
