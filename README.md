# erl-lang

Words rehearsal application

# Domain

## User
 * email
 * name
 * ll_token

## Dictionary Word
 - word in genereal. represents real word. may have links to some online distionaries. 
 - has property: language, utf8-16
 - has audio file of pronunciation
 - has list of Translations. Translation: language, text, translationId: trn-wordId-toSafeLowercalse(text)
User operates with `word_progress`es. 
## Word Progress
 - user added word in system, if we already have this word in system as Dictionary word, we give id, or create new DW.
 - some kind of lingualeo id
 - user may add translation(s) to the word.
 - we want to have a way to kind of sort translations, if there are a lot of them >1
 - each Translation has 'current_user_to_word_translation_status'
 - so word progress links DW_id, 'canonicalName', (translation, status)
 - Status: canonicalName, 0-100 score in our system, text description of status for user ?
 - here may be some logic coupling exercises and status 
 - word progress represent current state of word to it's translations being memorized by user
All User's Word Progresses are stored in User's Dictionary.
## Dictionary(Words belong to User)
 - user interacts with the system through the dictionary.
 - user can add words to dictionary from lingualeo via ll_token
 - user can see all words in her dictionary
 - words are sorted into Revise grops automatically
 - user can see all words in Revise group
the system remembers and updates user
 translation state of words in Revise groups using Exercises. for every day user is supposed  to know what words(Revise groups) she need to revise via exercises on lingualeo. 
The goal of user is to enhanse her vocabulary of words in a foreign language.
This is done via learning word->translation and translation->word meanings and then by repeating this process of getting knowledge again and again respawning it over some intervals. The repetition is the key here and the knowledge when to repeat what word is important. It is easily possible to learn about 20 new words a day and repeat what had already been learned. That way you can learn 1800 new words in a 3 months time and 3600 words in half of a year. Thats more than enough. And what do you do with ~3k words in a half of year lol.?
The role of lingualeo is as follows:  
 - it has good exercise system
 - it has nice extention that helps to translate words eng->ru and add it to lingualeo's wocabulary
 - supposedly we can authomatically add words to user's dictionary given his lingualeo_token 
 - and we can compose words in ll dictionary to groupes or stacks by lingua leo (ll) terms.
 - ll has great exercise system
 - ll has great firefox extention that helps to translate words in web and helps to add them to ll dictionary 
 - we can use ll api to get added words, group them into Revise group, stack them in ll distionary system, and send them to all ll exersices and update our own state of translation to word status, given that user will do exercises in ll. 
## FrequencyDictionary(Words in general grouped by frequency)
## Synonyms Dictionary(word to its synonyms set and lists by online dictionaries api)
## Exercise
## ReviseGroup


# Port/Adapters

## lingualeo api port&adapter
## data storage 
