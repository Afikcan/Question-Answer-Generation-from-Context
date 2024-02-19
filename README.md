# Question-Answer-Generation-from-Context
Brief description of your project, including its purpose and any unique technology or methodology it employs.
Training Phase

This project involves a training phase where we prepare our model for the main tasks. Here are the steps followed during this phase:
1. Download Squad Dataset, Preprocess and Save as CSV Files

    Objective: Download the Squad Dataset, preprocess it for our specific needs, and save the processed data in CSV format.
    Details: This step is crucial for ensuring that our model has the right format of data for training.

2. Train T5 Transformer Model

    Objective: Train the T5 transformer model using the preprocessed Squad Dataset.
    Details: The training process involves fine-tuning the T5 model to adapt it to our specific requirements and improve its prediction accuracy.

3. Test the Trained T5 Model

    Objective: Evaluate the trained model's performance and ensure it meets our expectations.
    Details: Testing is essential to verify the effectiveness of our model before moving on to the full project application.

Full Project

The full project encompasses several key activities aimed at extracting insights and generating content from text data:
1. Key Word Extraction

    Extract key words from texts to highlight the main focus areas.

2. Summarize Text

    Summarize the content based on extracted keywords for a concise overview.

3. Answer Span Extraction (Keywords and Noun Phrases)

    Identify specific answers or information in the text by focusing on relevant keywords and noun phrases.

4. Question Generation With T5

    Generate pertinent questions from the text using the T5 model, enhancing interactive learning and engagement.

5. Filter Keywords with Maximum Marginal Relevance

    Apply the Maximum Marginal Relevance technique to filter extracted keywords, reducing redundancy and emphasizing relevance.

6. Generate Match the Following Questions

    Create "match the following" questions for an interactive learning experience, requiring users to pair related items based on their understanding of the text.
