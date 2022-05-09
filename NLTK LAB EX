# LAB.1.

# 1.	Dla każdego z tekstów z NLTK Book należy wybrać dwa słowa i napisać kod, który zwraca wspólne konteksty występowania tych słów. 

import nltk
from nltk.book import *

teksty2 = [text1,text2,text3,text4,text5,text6,text7,text8,text9]

def zadanie():
    for text in teksty2:
        text.common_contexts(["stories", "pictures"])

zadanie()


# 2.	Korzystając z funkcji lexical_diversity (len(text) / len(set(text))- liczba liter w tekście podzielona przez liczbę różnych liter) uzupełnć poniższe tabelki dla danych z nltk.book 

import nltk
from nltk.book import *

def lexical_diversity():
    for element in teksty2:
        print('Lexical diversity dla tekstu:', element, ':', (len(element) / len(set(element))))


def liczba_slow():
    for element in teksty2:
        print('liczba słów dla tekstu:', element, ':', (len(element)))


def slowa_rozne():
    for element in teksty2:
        print('Słowa różne dla tekstu:',element, ':', (len(set(element))))


lexical_diversity()
print('--------------------------------------------------')
liczba_slow()
print('--------------------------------------------------')
slowa_rozne()


# 3. Stwórz listę wszystkich słów 4-literowych z text1. Ile ich jest? 

import nltk
from nltk.book import *

four_letter=[w for w in text1 if len(w)==4]
# print(four_letter)
print(len(four_letter))


# 4. W text1 znajd1 wszystkie wystąpienia słów długości większej niż 17. 

import nltk
from nltk.book import *

long_words=[w for w in text1 if len(w)>17]
print(long_words)



# 5. Podaj defnicję funkcji VocabSize(), która dla tekstu zwraca rozmiar słownika – czyli wylicza ile jest słów różnych. Zastosuj do każdego z tekstów z nltk.book. 

import nltk
from nltk.book import *


def VocabSize():
    for element in teksty2:
        print('Liczba słów różnych w:', element, 'to:', len(set(element)))


VocabSize()


# 6. Wyznacz 10 najczęściej występujących słów w text1. 

import nltk
from nltk.book import *


def vocab(text1):
   alpha = [word for word in text1 if word.isalpha()]
   return alpha


fdist1 = FreqDist(vocab(text1))
print(fdist1.most_common(10))


# 7. Sprawdź jakie są najdłuższe słowa w każdym z tekstów text1,..., text6. 

import nltk
from nltk.book import *


def longest_word():
    for element in teksty2:
        max_len = len(max(text1, key=len))
        print('Najdłuższe słowo dla tekstu:', element, 'to:', [word for word in text1 if len(word) == max_len])

longest_word()


# LAB.2.

import nltk

# 1. Przetestować przykłady z wykładu korpusy.

from nltk.corpus import wordnet as wn

dog=wn.synset('dog.n.01')
cat=wn.synset('cat.n.01')
animal=wn.synset('animal.n.01')
mammal=wn.synset('mammal.n.01')
bird=wn.synset('bird.n.01')
hen=wn.synset('hen.n.01')
entity=wn.synset('entity.n.01')

for w in [animal,mammal,dog,cat,bird,hen]:
    print(w, entity.path_similarity(w))


# 2. Sprawdzić nazwy plików w korpusie Gutenberg.

from nltk.corpus import gutenberg

for fileid in gutenberg.fileids():
    print(fileid)


# 3. Sprawdzić nazwy plików w korpusie Inaugural Address Corpus.

from nltk.corpus import inaugural

for fileid in inaugural.fileids():
    print(fileid)


# 4. Jakie kategorie występują w korpusie Movie Reviews.

from nltk.corpus import movie_reviews

for categorie in movie_reviews.categories():
    print(categorie)


# 5. Wydrukuj zdania występujące w korpusie Inaugural Corpus Address w pliku '1909-Taft.txt'.

from nltk.corpus import inaugural

zdania = (inaugural.sents('1909-Taft.txt'))
print(zdania)


# 6. Napisz skrypt, służący do sprawdzenia jak często w korpusie Brown w kategorii 'adventure' występują słowa 'mountains', 'ocean', 'Bungee jump'.

from nltk.corpus import brown
text = brown.words(categories='adventure')
fdist = nltk.FreqDist(w.lower() for w in text)
modals = ['mountains', 'ocean', 'Bungee jump']
for m in modals:
    print(m + ':', fdist[m], end=' ')


# 7. Wyszukaj 10 najczęsciej występujących słów w korpusie'’inaugural'.

from nltk.corpus import inaugural

slowa = inaugural.words()

def fr_words(inaugural):
    alpha = [word for word in inaugural if word.isalpha()]
    return alpha

fdist1 = nltk.FreqDist(fr_words(slowa))
print(fdist1.most_common(10))


# 8. Zdefiniuj funkcję, która dla tekstu zlicza jaki procent stanowią słowa spoza listy stopwords. Zastosuj funkcję do każdego z tekstów z NLTK Book.

from nltk.book import *
from nltk.corpus import stopwords


# 9. Sprawdź jaki jest wydźwięk słów: journalist, writer, actor, singer.

from nltk.corpus import sentiwordnet as swn

journalist = swn.senti_synset('journalist.n.01')
print(journalist)

writer = swn.senti_synset('writer.n.01')
print(writer)

actor = swn.senti_synset('actor.n.01')
print(actor)

singer = swn.senti_synset('singer.n.01')
print(singer)


# 10. Dla korpusu Gutenberg podać dla kazdego tekstu następujące dane: nazwa pliku, srednia liczba znaków w słowie, srednia liczba słów w zdaniu, srednia liczba powtórzeń tego samego słowa.

from nltk.corpus import gutenberg
for fileid in gutenberg.fileids():
    num_chars = len(gutenberg.raw(fileid))
    num_words = len(gutenberg.words(fileid))
    num_sents = len(gutenberg.sents(fileid))
    num_vocab = len(set(w.lower() for w in gutenberg.words(fileid)))
    print(fileid, round(num_chars/num_words), round(num_words/num_sents), round(num_words/num_vocab))



# 11. Polecenie

#    nltk.corpus.brown.tagged_words(tagset='universal')

# zwraca

#    [('The', 'DET'), ('Fulton', 'NOUN'),  ('Grand', 'ADJ'),
#    ('Jury', 'NOUN'), ('said', 'VERB'), ('Friday', 'NOUN'), ..

# Dla dokumentu cr09 z korpusu Browna wylicz częstosci wystąpień słów z poszczególnymi znacznikami z listy uproszczonej. Jakie znaczniki są najczęstsze?

from nltk.corpus import brown

nltk.corpus.brown.tagged_words(tagset='universal')
brown_news_tagged = brown.tagged_words(fileids='cr09', tagset='universal')
tag_fd = nltk.FreqDist(tag for(word, tag) in brown_news_tagged)
print(tag_fd.most_common())

