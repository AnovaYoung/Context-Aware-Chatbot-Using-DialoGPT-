**Preprocessing for DialoGPT Fine-Tuning**

Overview
This document outlines the preprocessing steps taken to prepare the Cornell Movie Dialogs Corpus for fine-tuning DialoGPT. These steps ensure the text data is cleaned, tokenized, padded, and structured in a way that is compatible with the DialoGPT model.

Steps Taken in Preprocessing

Step 1:

Text Cleaning and Normalization
Objective: Clean the dialogue text by lowercasing all characters and removing unnecessary special characters while preserving punctuation for conversational flow.

Actions:
Converted all text to lowercase.
Removed special characters except for punctuation marks such as .,!?.
Normalized white spaces.

Step 2: 

Stop Word Removal with Retained Pronouns and Conversational Fillers
Objective: Remove common stop words to reduce noise while keeping important conversational elements such as pronouns and conversational fillers.

Actions:
Removed typical stop words (e.g., "the," "is," "at").
Retained pronouns (e.g., "he," "she," "they") and conversational fillers (e.g., "yeah," "okay") as they are crucial for dialogue generation.

Step 3: T

okenization Using DialoGPT’s Pre-trained Tokenizer
Objective: Convert the cleaned and processed text into token IDs using DialoGPT’s tokenizer.

Actions:
Used Byte-Level Byte Pair Encoding (BPE) with DialoGPT’s tokenizer to convert each utterance into token IDs.
Ensured that the text includes the necessary special tokens (e.g., end-of-sequence tokens).

Step 4: 

Padding and Truncating Sequences
Objective: Ensure all tokenized sequences are of uniform length by padding shorter sequences and truncating longer ones.

Actions:
Added a padding token ([PAD]) to the tokenizer.
Applied padding to shorter sequences and truncated longer sequences to a maximum length of 50 tokens.

Step 5: 

Creating Attention Masks
Objective: Create attention masks to inform the model which tokens are padding and which are real data.

Actions:
Generated attention masks, where 1 represents real tokens and 0 represents padding tokens.

Step 6: 

Structuring the Dataset for Model Input
Objective: Prepare the dataset in a format compatible with PyTorch for training.

Actions:
Created a custom PyTorch Dataset class to handle input IDs and attention masks.
Set up a DataLoader to batch the dataset for training.
