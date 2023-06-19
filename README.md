# Language Processing Possibilities in Hinglish

### Aim: 
The Aim for the project was to explore the language processing possibilities in Hinglish using established practises in Hindi and English.

### Objectives: 
To achieve the goal, we divided the problem into smaller tasks. The associated objectives are as follows:
* Coming up with a definition for Hinglish
* Finding a suitable corpus for language analysis.
* Studying derived words in English and Hindi
* Analysis of the language(Hinglish) structure and possibility of a POS tagger
* Exploring parsing with simple POS tagging

### Software and Corpus: 
To accomplish our work, we have used the following:
* Toolkits: NLTK
* Online Software : Google Translate
* Code mixed corpus for Hinglish : One provided on Piazza
* Sentences for parsing : Twitter, advetisements, movie dialogues, some personal sentences

### Some Issues and Plan of Action:
Even with the tools we are using, there are certain problems inherent in the analysis. These are:
* Unavailability of a POS tagged corpus
* Encoding issues with corpora online 
* Small model size of NLTK models for Hindi

While the above might seem to be trivial problems, in practise they aren’t.  Since we were unable to find actual Hinglish corpus, we had make do with the one we were provided. All other corpora, while code mixed were not Hinglish in essence. They were mere Hindi sentences with English translation. 
Another issue was that of small size of NLTK corpus for Hindi. This corpus had a weak vocabulary when it came to analysing English derived words. Hence we had to rely on google for all such analysis. 

### Corpus:
The corpus had the following problems:
* EOL characters were not properly coded
* Amongst all its sections, only the auto_news section of Hindi news was  liberally using Hinglish. Thus we chose to analyse it only. Others had very low percentage of English dictionary words.
* There was issue with punctuations. 
* While English vocabulary was frequently used, issues with its POS tagging and further analysis had to be stalled because these were written in the Devanagari script. Further, the indicated English words did not have the same Devanagari spelling in most instances. 

### What is Hinglish?
A fundamental problem is to come up with some definition for Hinglish. The language has been in the scene since British ever came. During their time in India, the British borrowed a large vocabulary from us. This includes words like “Jungle”, “karma”, “tantric”, “shampoo”, “juggernaut”, etc. Thus sentences like “Jungles of Arizona are beautiful”, is a legit English sentence. Similarly, words like ‘car’, ‘rocket’ have made it to Hindi as well, and so “vah police me the” is a legit Hindi sentence.

But merely using derived words does not amount to speaking Hinglish. However, words like “Lathi Charge” and “Policewala” indicate the language in brewing.  

In our analysis, considering the corpus limitations, we have considered only those sentences as Hinglish, which are used more frequently against their pure single language counterparts and have either of the noun, adjective or the verb in a different language.

### Observations on Derived words:
* English and Hindi are two structurally different languages. While Hindi follows a Subject-Object-Verb syntax, English follows the Subject-Verb-Object scheme. 
* Also, chunks in Hindi can be moved without changing the meaning while in English this is not possible.  
* The syntax deciding elements in the grammar are the verbs and the prepositions.
* Also, since the use of determiners in both languages is different, they may also be used to differentiate. 
* Thus a grammar involving both is bound to be very complicated.
* Most of the derived words in either languages (from each other) are nouns and adjectives. 
* Proper nouns are also changed to suit the phonetic convention of the receiving languages and thus the spelling in such derivation can also change.

### Code:
[Click here for code](Language.ipynb)


### Implications and hypothesis:
The above observations point towards the possibilities in grammar of Hinglish. These are as follows :
* The inherent structure of a sentence in Hinglish is either that of English or Hindi. 
* The different noun phrases of the sentence might be of different language.
* The language of the verb and that of the prepositions must be in agreement.

### POS tagging:
The corpus was flawed and thus we had to take the following procedure:
* Processed the corpus to solve encoding and punctuation errors.
* Extracted all English words written in Devanagari
* Converted all extracted words into a dictionary and translated them using Google Translate. This roughly corresponds to converting their script.
* Replaced them with their devanagari counterparts and read the corrected corpus into the backoff  Hindi tagger. 
* The words left out by the above tagger are tagged by a English tagger.

While the above tagging scheme is working fine enough and seems to be correct, there is no concrete way to check this without a sizeable tagged corpus. Manual checking had been done in a few randomly extracted sentences in the code.

### Parsing for few hand picked Hinglish sentences

#### Input:
[Click here for input code](Input File.txt)

#### Output:
[Click here for output](Output File.txt)


### Observations:
The analysis left me with POS tagged corpus for Hinglish. While we may not assume reliability on the exact number, the frequencies indicate the following:
* While their relative proportions might vary, the nouns are clear winners.
* The structure deciding elements, ie. , verbs and prepositions, etc are more frequently from Hindi
* The noun, adjective and even the Proper nouns are English.
* The determiner count from Hindi is negligible.
