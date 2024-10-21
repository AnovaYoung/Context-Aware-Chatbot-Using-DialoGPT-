# Context Aware Chatbot Using DialoGPT/GPT-4 and the Cornell Movie Corpus

---

### **Project Overview**

This project involves building and comparing conversational models using the **Cornell Movie Dialogs Corpus**. Two primary models were used for this chatbot:

1. **DialoGPT** (both small and large versions) – a fine-tuned conversational model based on GPT-2.
2. **GPT-4** – the most advanced GPT model from OpenAI, used directly via the OpenAI API.

The goal of this project was to fine-tune and evaluate the performance of both models in generating natural, coherent responses using movie dialogs as input. The performance was evaluated using **BLEU** and **ROUGE-L** metrics.

---

### **Data**

**Dataset**: The Cornell Movie Dialogs Corpus consists of character lines and conversations extracted from various movies.

- **Lines Data**: Contains individual character lines (movie quotes) along with metadata like the movie ID and character ID.
- **Conversations Data**: Contains the list of exchanges between characters, each linked to specific lines from the Lines Data.

---

### **Project Steps**

1. **Data Preprocessing**
    - **Data Cleaning**: Removed missing or irrelevant information from the lines and conversations datasets.
    - **Truncation**: Applied truncation to limit the conversation length to 512 tokens to fit within the model's context window for GPT-4.
    - **Handling Special Tokens**: No tokenization or padding was required for the GPT-4 model. For DialoGPT, padding tokens were added where necessary.

2. **Model Implementation**
    - **DialoGPT (Small and Large)**:
      - Both the small and large DialoGPT models were fine-tuned on the movie dialogs dataset using **PyTorch**.
      - Techniques such as **gradient accumulation** were used to optimize memory usage and stabilize training.
      - The models were trained for multiple epochs, and further fine-tuning was performed with techniques like learning rate scheduling.
    
    - **GPT-4**:
      - GPT-4 was accessed via the OpenAI API. Tokenization and padding were not needed, but truncation was applied for longer conversations.
      - Batch processing was implemented to efficiently handle multiple conversations simultaneously.

3. **Model Evaluation**
    - **BLEU Score**: Evaluates the similarity between the generated responses and the actual human responses in the dataset.
    - **ROUGE-L Score**: Measures the longest common subsequence between the generated and reference responses.
    - **Accuracy**: DialoGPT models were also evaluated based on their ability to generate responses closely matching the expected human response.

---

### **Performance Results**

**DialoGPT (Small)**
- **Final Loss**: ~1.19 after fine-tuning
- **Perplexity**: 2.46
- **Final Scores**: 
  - BLEU: 0.777
  - ROUGE-L: 0.916
  - Accuracy: 0.758

**DialoGPT (Large)**
- **Final Loss**: 0.896 after fine-tuning
- **Final Scores**: To be added

**GPT-4**
- **BLEU Score**: 0.107 (initial evaluation)
- **ROUGE-L Score**: 0.423 (initial evaluation)
- **Truncation Applied**: Conversations truncated to 512 words for input efficiency.
- **Batch Processing**: Used for handling conversations in groups.

---

### **Key Techniques**

- **Gradient Accumulation**: This technique was used to accumulate gradients across smaller batches, allowing for more stable training when memory resources were limited, particularly for the DialoGPT-Large model.
- **Batch Processing**: Implemented for GPT-4 to improve model efficiency and runtime by sending multiple conversation inputs at once.
- **Truncation**: Applied to both DialoGPT and GPT-4 to reduce input length and avoid exceeding the token limits.

---

### **How to Run**

1. **Data Preparation**:
    - Download the Cornell Movie Dialogs Corpus.
    - Ensure the data is properly cleaned and formatted.
  
2. **Model Training** (for DialoGPT):
    - Run the training scripts provided for both small and large DialoGPT models.
    - Adjust the number of epochs, learning rate, and other hyperparameters as necessary.

3. **Model Inference**:
    - For **GPT-4**: Utilize the OpenAI API to generate responses based on the cleaned conversation inputs.
    - For **DialoGPT**: Use the fine-tuned model to generate responses from the input dataset.

4. **Evaluation**:
    - Run the evaluation scripts to calculate BLEU, ROUGE-L, and accuracy for each model.
    - Compare the results between DialoGPT and GPT-4.

---

### **Dependencies**

- **Transformers** by Hugging Face
- **PyTorch**
- **OpenAI API** (for GPT-4)
- **Evaluate** (for BLEU and ROUGE-L score evaluation)
- **NLTK** (for text tokenization)

---

### **Acknowledgments**

This project utilized the Cornell Movie Dialogs Corpus and leveraged both OpenAI's GPT models and Hugging Face's Transformers library. Special thanks to the open-source contributors who make these resources available.

---

