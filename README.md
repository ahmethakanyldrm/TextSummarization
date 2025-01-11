# Text Summarization with SpaCy

This project implements a text summarization tool using **SpaCy**, an NLP library. The summarizer extracts the most important sentences from a given text by analyzing word frequencies, filtering out stop words and punctuation, and scoring sentences based on their word frequencies.

## Table of Contents

- [Usage](#usage)
- [How It Works](#how-it-works)
- [Dependencies](#dependencies)



### Prerequisites
- Python 3.x
- **SpaCy** library
- **en_core_web_sm** model
- **Flask**



## Usage
To use the summarizer, you can call the summarizer function with your text input. Here's an example:

   ```python
  from summarizer import summarizer
  rawdocs = "Your long document text goes here..."
  summary, doc, original_len, summary_len = summarizer(rawdocs)
  
  print("Summary:", summary)
  print("Original length (words):", original_len)
  print("Summary length (words):", summary_len)
```
The function will return:

 A summarized text (summary)
The processed text document (doc)
The original text length in words (original_len)
The length of the summary in words (summary_len)

## How It Works
Text Preprocessing:

The text is passed through SpaCy's NLP pipeline to split it into tokens (words and punctuation).
Stop words (e.g., "the", "and") and punctuation marks are filtered out.
Word Frequency Calculation:

A frequency distribution of the non-stop words is created. This represents the importance of each word in the text based on how frequently it appears.
Sentence Scoring:

Each sentence in the text is scored based on the frequency of its words. The more frequently a word appears, the higher the sentence's score.

Summarization:

The top 30% of sentences (by score) are selected to form the summary.
These sentences are then joined together to produce the final summary.

## Dependencies
SpaCy: Used for natural language processing tasks such as tokenization, sentence segmentation, and stopword handling.
heapq: A built-in Python module used to extract the top n highest scoring sentences.
