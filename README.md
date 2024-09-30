# Context-Aware-Chatbot-Using-DialoGPT

In this project, I aim to develop a chatbot capable of engaging in coherent, multi-turn conversations across a variety of topics while maintaining contextual awareness. By fine-tuning the pre-trained Transformer model DialoGPT using the Cornell Movie Dialogs Corpus, the chatbot will learn to generate contextually relevant and natural-sounding responses. 

The primary objectives are to:

•	Leverage advanced natural language processing techniques to create a conversational AI that can adapt to multi-turn dialogues.

•	Fine-tune DialoGPT to align with the conversational style and diversity found in movie dialogues.

•	Evaluate the chatbot's performance in terms of response relevance, coherence, and context.

•	Develop a user-friendly interface where users can interact with it in real-time.

**Description of Selected Dataset**

**The Cornell Movie Dialogs Corpus** is a collection of fictional conversations from movie scripts. Its great for training and evaluating conversational agents because of its richness and diversity in dialogue.

**Data Source:** https://www.kaggle.com/datasets/rajathmc/cornell-moviedialog-corpus

**Contents:**

Number of Movies: 617

Number of Characters: Over 10,000

Number of Conversations: Approximately 83,000

Number of Utterances (Lines): Around 304,000

Languages: Primarily English

**Structure:**

movie_lines.txt: Contains individual lines of dialogue with fields:

Line ID: Unique identifier for each line.

Character ID: Identifier for the character speaking.

Movie ID: Identifier for the movie.

Character Name: Name of the character.

Utterance Text: The actual dialogue line.

movie_conversations.txt: Defines the conversations by listing sequences of line IDs that form each dialogue between pairs of characters.

**Size of Dataset:**

The total dataset size is approximately 20 MB in plain text format.
