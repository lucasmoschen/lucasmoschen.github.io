---
layout: page
title: "Search Engine"
description: "Implementation of a search engine for Data Structures and Algorithms
class, implemented with Alessandra Cid and Lucas Resck."
img: assets/img/search-engine.png
importance: 3
category: 2019
---

Implementation of a search engine for Data Structures and Algorithms class, implemented with [Alessandra Cid](https://github.com/alessandracid) and [Lucas Domingues](https://github.com/lucasresck). 
It's our final project for the subject [Data Structure and Algorithms](https://emap.fgv.br/en/discipline/graduacao-matematica-aplicada-graduacao-ciencia-de-dados/data-structures-and-algorithms). 


Abstract 
---

For this project our group developed a search engine that searches for a word, or multiple words, in the English portion of the Wikipedia corpus. In order to do that, we constructed a trie in C++ to use as our data structure. We used Python to pre-process the corpus and then inserted it into the trie. Our search is also done in C++. If we have more than one word, we compare the pages that are common to all words and only return them. If a user misspells a word when searching, our program returns suggestions for alternative results. 

Repository 
---

This is the link to the group's Github repository containing all of the [project's source code](https://github.com/lucasmoschen/search-engine).
In order to run the program you should download [this
file](https://bit.ly/2WYQing) and follow the [README](https://github.com/lucasmoschen/Search-engine/blob/master/README.md).

Description
---

The [Wikipedia corpus](http://www.cs.upc.edu/~nlp/wikicorpus) as several
different text files. Each file contained one or more Wikipedia pages. The
first step in the project was to pre-process, in Python, this data. Some non
ASCII and ASCII symbols were removed, but all of the numbers and some symbols.
All of the accents from the words that had them were also eliminated and the
letters in upper case were transformed into lower case. 

For the data structure, the group first chose to build a [suffix
tree](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-851-advanced-data-structures-spring-2012/lecture-videos/session-16-strings/).
A suffix tree is a compressed trie that stores all the suffixes of a given
text. The first letter of each suffix starts as a node from the root of the
tree and the other letters are the child of that node. If a node only has one
child, the child and parent node are compressed into a single node. This
structure was built by going through the text files that corresponded to the
Wikipedia pages and inserting it's suffixes. After building this structure and
a search function for it, the group concluded that it would take too much time
to insert the Wikipedia corpus into the suffix tree. The group decided, then,
to build a trie. 

A trie is a tree that stores different words. In this case, all the words in the Wikipedia corpus. Each letter of a word in the trie is the child of the letter that came before it in the word. 
For this project, the trie was constructed by going through the words in the
text files. Each word in the file that wasn't already in the trie by the time
it was reached, was inserted into it. In order to identify the Wikipedia pages
that contained each word, a pointer to an array named docs was placed in each
node. These arrays stored numbers identifying each of the pages in which a
certain word appears. They could be accessed through the node related to the
last letter in the word. 

To build this in C++, pointers were used. Each pointer had 128 potential
*child* pointers corresponding to a specific ASCII character. If a person
wants to verify if a specific word is in the trie, they can start from the
root of the trie and visit the child corresponding to the ASCII character of
each of the letters in the word. If they were able to reach the node
corresponding to the last letter in the word, it means that in at least one
Wikipedia page that word exists. Accessing the array docs from that point
allows the person to see the number corresponding to those pages.

The user can enter a query: it is pre-processed, removing accents and lowering the case of letters in upper case. Then, each word in the query is identified and searched, by accessing the child of each of the word's letters in the trie. This search is done in linear time, varying on the length of what was searched. If the word searched exists in one or more Wikipedia page, the number corresponding to those pages is inserted into an array. If that word does not exist, the program runs a minimum edit distance algorithm to identify similar expressions and returns the ones that appear the most in Wikipedia pages. This way, the search returns a popular word similar to the one searched by the user. 
If a query has more than one word, each time the program searches for a new word it compares the previous document array that it had with the new searched one and only keeps the pages that are common to both. As the page numbers are ordered in each array, this is done in linear time in relation to the number of documents. 
After the search ends, the program returns the number of results that were found and identifies the title of each page found in the search. The title of the 20 first results are then displayed in alphabetical order. The user is able to open in details an specific page that returned as a result or to see the title of 20 more pages found in the search. 

