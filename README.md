# MCQS Generator Using Machine learning : Natural Language Processing

# Project Link : 
https://mcq-generator-eta.vercel.app

# Introduction:

This project aims to generate multiple-choice questions (MCQs) using machine learning and natural language processing (NLP) techniques. MCQs are widely used in educational assessments to evaluate students' understanding of a given topic. By automating the generation of MCQs, educators can save time and effort while ensuring the quality and relevance of the questions.





# Code:

### Load English tokenizer, tagger, parser, NER, and word vectors
nlp = spacy.load("en_core_web_sm")

### Input text

text = """
Nature's beauty is an endless source of wonder and inspiration, offering solace and peace to those who take the time to immerse themselves in it. Whether it's the vibrant hues of a sunset stretching across the horizon or the quiet majesty of towering mountains, nature has a way of reminding us of the vastness of the world beyond our daily routines. The delicate balance within ecosystems, from the smallest insect to the tallest tree, demonstrates the intricate connections that sustain life. The sounds of nature—the rustling of leaves, the gentle flow of rivers, or the distant call of birds—create a soothing symphony that calms the mind. In a world where technology and fast-paced living often dominate, spending time in nature can ground us, reminding us of the simplicity and beauty in the natural rhythms of the earth. It's a gentle reminder that despite the complexities of life, there's a sense of peace to be found in the world around us.
"""
### Number of questions
num_questions=5

### Process the text with spaCy

doc = nlp(text)

### Extract sentences from the text

sentences = [sent.text for sent in doc.sents]

### Randomly select sentences to form questions

selected_sentences = random.sample(sentences, min(num_questions, len(sentences)))
selected_sentences


# Explanation of the Code:

### Loading Modules:

The code begins by importing necessary modules, including spacy for NLP processing and random for random selection of sentences.

### Loading English Language Model:

It loads the English language model from spaCy (en_core_web_sm) for tokenization, tagging, parsing, named entity recognition (NER), and word vectors.


### Input Text:

The input text contains information about the Nile River, its significance, and characteristics.

### Processing the Text:

The input text is processed using spaCy, which tokenizes the text into words, identifies parts of speech, parses the structure, recognizes named entities, and generates word vectors.

### Extracting Sentences:

The processed text is split into sentences, and each sentence is stored in a list named sentences.
Randomly Selecting Sentences:
Randomly selects a subset of sentences from the list of sentences to form questions. The number of questions to generate is specified by num_questions.


###  Result:
The selected sentences are stored in the selected_sentences list, which will be used to generate MCQs.





# Working:


- Initialize List for MCQs: It starts by creating an empty list to store the generated MCQs.


- Generate MCQs for Each Sentence: It iterates through each sentence in the selected_sentences list.


- Process Sentence with spaCy: It uses spaCy (nlp) to process each sentence and tokenize it.


- Extract Nouns: It extracts nouns from the sentence by filtering tokens with the part-of-speech tag "NOUN".


- Ensure Enough Nouns: It checks if there are at least two nouns in the sentence. If not, it continues to the next sentence.


- Count Noun Occurrences: It counts the occurrence of each noun in the sentence.


- Select Subject: It selects the most common noun in the sentence as the subject of the question.


- Generate Question Stem: It creates the question stem by replacing the subject noun with a blank ("_______").


- Generate Answer Choices: It generates answer choices by including the subject noun as one choice and randomly selecting three 


- Distractors from the other nouns in the sentence.


- Shuffle Answer Choices: It shuffles the answer choices to avoid any bias.


- Append MCQ to List: It appends the generated MCQ (question stem, answer choices, and correct answer) to the list of MCQs.


- Return MCQs: Finally, it returns the list of generated MCQs.

# Snaps of the project:

![Screenshot (4648)](https://github.com/user-attachments/assets/45f8b87a-98b9-4afd-997e-886f45ec06ee)

![Screenshot (4649)](https://github.com/user-attachments/assets/ec54224a-6292-4b80-bb14-2d5334f20a72)

![Screenshot (4651)](https://github.com/user-attachments/assets/3ca5b5bf-8131-4125-94c9-ebe3b4f6e221)



This code can to be a useful tool for automatically generating multiple-choice questions from text data, which could be helpful for educational purposes or generating practice quizzes. You can discuss how this functionality can save time for educators or content creators and how it leverages natural language processing techniques to automate the process. Additionally, you can mention potential improvements or customization options, such as adjusting the number of distractors or incorporating more sophisticated language processing techniques.


