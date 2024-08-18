# AI-Simulated-Lawyer-Course-Project

Final project for the Building AI course

## Summary

 The main idea behind this project is to create a powerful, or at least sufficiently capable, AI method that assists people in identifying situations requiring legal help. Additionally, it aims to enhance understanding of legal matters based on information available online. As a foundation, any websites allowing information sharing and use could be implemented as a legal basis or database. Examples include official government sites or wiki pages.
 My vision for this AI method is that it will answer questions precisely, drawing from previously discussed information. It will also help determine whether individuals can resolve legal issues independently or if they need legal assistance. Given the variation in legal frameworks across different countries, this AI method will focus on questions related to specific legal contexts or, where applicable, international laws. Importantly, user information should remain private and not be stored for any other purposes.
 To make this project successful, we should employ the following algorithms, models, and techniques: Natural Language Processing (NLP), machine learning algorithms, and generative language models. The AI method will interact with users as a chatbot, and user feedback will be crucial for continuous improvement. When faced with ambiguous questions, the AI should identify the main issues by asking additional questions or analyzing connections to legal frameworks before providing answers. Additionally, neural networks can be employed for intent classification.

## Background

Solves common legal problems that could arise frequently by giving the right advice or directing the person in the right direction, including whether it's a legal issue and can be currently solved.

## How is it used?

It's a legal assistant chatbot that helps with issue identification and possible solutions.

```
import spacy
from gpt4all import GPT4All

#model = GPT4All("Meta-Llama-3-8B-Instruct-IQ4_NL.gguf")  # Downloads / loads a 4.66GB LLM, unless already downloaded to desired location, then look below

# Specify the path to the downloaded model file
model_path = "/path to your directory/Meta-Llama-3-8B-Instruct-IQ4_NL.gguf"

# Initialize the GPT4All model
model = GPT4All(model_path)

with model.chat_session():
    response = model.generate("How can I run LLMs efficiently on my laptop?", max_tokens=1024)
    print(response)

# Load the spaCy NLP model
nlp = spacy.load("en_core_web_sm")

# Example legal text (a more comprehensive dataset is needed)
legal_text = """
This is a sample legal text. It contains relevant information about laws and regulations.
"""

# Preprocess the legal text
doc = nlp(legal_text)

# Extract legal concepts (e.g., named entities)
legal_concepts = [ent.text for ent in doc.ents]

# Simulate user queries (replace with actual user input)
user_query = "What are the requirements for starting a business?"

# Intent recognition (simplified rule-based approach)
def get_gpt_response(user_query):
    messages = [
        {"role": "user", "content": user_query}
    ]
    response = model.generate_response(messages)
    return response

# Example usage
gpt_response = get_gpt_response(user_query)
print(gpt_response)
```

## Challenges

This chatbot won't be able to solve solutions by itself but should be understood as a legal assistant

## What next?

This project requires good python programmers, AI engineers or people with good knowledge of AI to build it and, obviously, their collaboration.

## Acknowledgments

This project was inspired by Elements of AI courses: https://www.elementsofai.com/

AI support was used while writing this readme file, and what partially inspired this project, in the first place, too(what is an implementation of ChatGPT in Microsoft ChatBot/Search): https://copilot.microsoft.com/

GPT4All was used in newest versions of prototype: https://github.com/nomic-ai/gpt4all

The Meta-Llama-3-8B-Instruct-IQ4_NL.gguf model from the Hugging Face Model Hub was used also: https://huggingface.co/bartowski/Meta-Llama-3-8B-Instruct-GGUF.
