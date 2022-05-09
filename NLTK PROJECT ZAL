import nltk
from nltk.corpus.reader import CategorizedPlaintextCorpusReader
from stopwordsiso import stopwords
option = 1


my_corpus = CategorizedPlaintextCorpusReader('/Users/annaciesniewska/Desktop/CORPUS_PROJEKT', r'movie._.*\.txt', cat_pattern=r'movie._(\w+)\.txt')
categories = my_corpus.categories()



# WORDS PREPARATION

def prepare_words(text, with_stopwords=True, min_length=1):
    words = []
    for word in text:
        if str.isalpha(word) and len(word)>=min_length:
            word_lower = str.lower(word)
            if with_stopwords or word_lower not in stopwords("en"):
                words.append(word_lower)
    return words

# CATEGORIZATION

neg = my_corpus.words(categories=['neg'])
pos = my_corpus.words(categories=['pos'])


# WORDS LENGTH

def longest_word_length(text):
    maxlen = max(len(word) for word in text if str.isalpha(word))
    return maxlen

def words_of_length(text, length):
    word_set = set()
    for word in text:
        if len(word) == length and str.isalpha(word):
            word_set.add(str.lower(word))

    length_word_set = len(word_set)

    if length_word_set:
        print('The longest word has', length, 'characters:', word_set)
    if length_word_set == 1:
            print('There is', length_word_set, 'word with this number of characters.')
    else:
            print('There are', length_word_set, 'words with this number of characters.')


def longest_words(text):
    maxlen = longest_word_length(text)
    words_of_length(text, maxlen)

# MOST COMMON WORDS

def most_common_words(text, number):
    words = prepare_words(text, False, 2)
    freq_dist = nltk.FreqDist(words)

    print(number, 'most common words:', freq_dist.most_common(number))
    print()

# NUMBER OF WORDS IN A GIVEN TEXT

def number_of_words(chosen_text):
    first_positive = my_corpus.words(chosen_text)
    print(len(first_positive))


# MENU

while option != 0:
    print('~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~')
    print('OPTIONS:')
    print('1 - CORPUS CATEGORIES')
    print('2 - LIST OF TEXTS')
    print('3 - LIST OF TEXTS USED IN EACH CATEGORY')
    print('4 - THE LONGEST WORDS')
    print('5 - THE MOST COMMON 10 WORDS')
    print('6 - NUMBER OF WORDS IN A GIVEN TEXT')
    print('~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~')
    option = input('Choose your option: ')
    print('')

    if option == '1':

        print('Categories present in the corpus:', categories)

    elif option == '2':

        print('List of texts used in the corpus', my_corpus.fileids())

    elif option == '3':

        print("\nNegative field : ", my_corpus.fileids(categories=['neg']))

        print("\nPositive field : ", my_corpus.fileids(categories=['pos']))

    elif option == '4':

        print('THE LONGEST WORDS FOR:')
        print('')
        print('Negative reviews:')
        longest_words(neg)
        print('')
        print('Positive reviews:')
        longest_words(pos)
        print('')
        print('Whole corpus:')
        longest_words(my_corpus.words())

    elif option == '5':

        print('MOST COMMON WORDS')
        print('')
        print('Negative reviews:')
        most_common_words(neg, 10)
        print('Positive reviews:')
        most_common_words(pos, 10)

    elif option == '6':

        print('NUMBER OF WORDS IN A GIVEN TEXT')
        print('')
        print('List of texts used in the corpus', my_corpus.fileids())
        chosen_text = input(str('Choose your text:'))
        number_of_words(chosen_text)


    else:
        print('Error')




