# Glaucoma Chatbot

This Glaucoma Chatbot project provides answers to glaucoma-related questions by using two different embedding models: **BioBERT** and **BioWordVec**. The chatbot returns two responses—one from each model—along with confidence scores for each answer. This project demonstrates how to leverage pretrained embeddings to match questions and answers in a conversational chatbot.

## Table of Contents
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Setup](#setup)
- [Usage](#usage)
- [Acknowledgments](#acknowledgments)

---

## Features
- **BioBERT Model** for biomedical question-answering tasks.
- **BioWordVec Model** for fast and efficient word embeddings in the biomedical domain.
- **Cosine Similarity** to find the most relevant answer for user questions.
- **Confidence Scores** for BioBERT and BioWordVec responses to evaluate answer relevance.

## Project Structure
```plaintext
.
├── Combined_Dataset.xlsx    # Dataset containing questions and answers related to glaucoma
├── bio_embedding_intrinsic   # BioWordVec model file (should be in binary format)
├── precomputed_embeddings.pkl # (Optional) File for storing precomputed embeddings
└── chatbot.py               # Main script to run the chatbot

Installation
Prerequisites
Python 3.7+
PyTorch (version compatible with your CUDA setup if using GPU)
Required Python packages:
transformers
gensim
numpy
pandas
scikit-learn
Step-by-Step Installation
Clone the repository (or download the code files directly):

bash
Copy code
git clone <repository-url>
cd <repository-folder>
Create a virtual environment (optional but recommended):

bash
Copy code
python3 -m venv glaucoma-chatbot-env
source glaucoma-chatbot-env/bin/activate  # For Linux/Mac
glaucoma-chatbot-env\Scripts\activate     # For Windows
Install the required packages:

bash
Copy code
pip install torch transformers gensim numpy pandas scikit-learn
Download the BioBERT model: The BioBERT model will be downloaded automatically when you run the code, as it's specified by the Hugging Face model ID dmis-lab/biobert-base-cased-v1.1.

Download the BioWordVec model: Place the BioWordVec model file (bio_embedding_intrinsic) in the same folder as your project files. Ensure it’s in the correct format (binary).

Dataset: Ensure you have the file Combined_Dataset.xlsx containing the Q&A data in the project directory. This dataset should have columns named exactly as Question and Answer.

Setup
1. Verify Data Format
Ensure that Combined_Dataset.xlsx is formatted correctly, with columns named exactly as Question and Answer.

2. Precompute Embeddings
Precompute embeddings by running the main script. This will save the embeddings to a pickle file (precomputed_embeddings.pkl) for faster future use.

bash
Copy code
python chatbot.py
Usage
Run the Chatbot

bash
Copy code
python chatbot.py
Interact with the Chatbot

The chatbot will prompt you to ask questions related to glaucoma.
Type your question and press Enter.
The chatbot will respond with answers from both BioBERT and BioWordVec, along with confidence scores.
Exit the Chatbot

Type exit to close the chatbot.
Sample Chat
plaintext
Copy code
Hey there..! I'm Glaucoma Chatbot!
You can ask any question related to glaucoma or type 'exit' to stop.

Your question: What are the symptoms of glaucoma?
--- BioBERT Response ---
Matched Question: What are the primary symptoms of glaucoma?
Answer: The primary symptoms include blurred vision, eye pain, etc.
Confidence: 0.85

--- BioWordVec Response ---
Matched Question: Symptoms of glaucoma?
Answer: Blurred vision, headaches, and seeing halos.
Confidence: 0.82

Your question: exit
Thank-You!
Troubleshooting
Model Not Found: Ensure the BioWordVec model (bio_embedding_intrinsic) is in the project directory and in binary format.
CUDA Errors: If using GPU, make sure your PyTorch version is compatible with your CUDA version.
Embeddings File Not Found: If you encounter issues with precomputed_embeddings.pkl, rerun the script to regenerate the file.
Acknowledgments
This project utilizes:

BioBERT by DMIS Lab, trained specifically for biomedical text.
BioWordVec, a word embedding model tailored to biomedical terms and vocabulary.

