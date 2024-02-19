# Question-Answer-Generation-from-Context
The main objective of the project is to develop a system that can automatically generate questions from a given context using the T5 model. In addition to the main objective, it is also aimed to generate one correct answer to this question and three strongly misleading answers that make it difficult to know this answer. This system focuses on the capacity to generate contextually relevant and meaningful questions, with particular applicability in the field of education.
## Training Phase

This project involves a training phase where we prepare our model for the main tasks. Here are the steps followed during this phase:
### 1. Download Squad Dataset, Preprocess and Save as CSV Files

Objective: Download the Squad and Race Dataset and merge them, preprocess it for our specific needs, and save the processed data in CSV format.
Details: This step is crucial for ensuring that our model has the right format of data for training.

### 2. Train T5 Transformer Model

Objective: Train the T5 transformer model using the preprocessed merged Dataset.
Details: The training process involves fine-tuning the T5 model to adapt it to our specific requirements and improve its prediction accuracy.

### 3. Test the Trained T5 Model

Objective: Evaluate the trained model's performance and ensure it meets our expectations.
Details: Testing is essential to verify the effectiveness of our model before moving on to the full project application.

## Full Project

The full project encompasses several key activities aimed at extracting insights and generating content from text data:
### 1. Summarize Text

Summarize the content based on extracted keywords for a concise overview.

### 2. Answer Span Extraction (Keywords and Noun Phrases)

Extract key words from texts, identify specific answers or information in the text by focusing on relevant keywords and noun phrases. In this way we can use extracted keywords as our answers. 

### 3. Question Generation With T5

Generate pertinent questions from the text using the T5 model by giving out answer with text, enhancing interactive learning and engagement.

### 4. Generate Wrong Answers From Answer

Using two different method (sense2vec and WordNet), we extract keywords from our keyword/answer. 

### 5. Filter Keywords with Maximum Marginal Relevance

Apply the Maximum Marginal Relevance technique to filter extracted keywords, reducing redundancy and emphasizing relevance. We get best 3 results to use them as our wrong answers.

In the end, we have 1 question, 3 wrong answers and 1 correct answer. 
