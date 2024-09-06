# Question-Answer Generation from Context

## Table of Contents
- [Introduction](#introduction)
- [Research Questions](#research-questions)
- [Dataset](#dataset)
- [Usage](#usage)
- [Approach](#approach)
  - [Model Architecture](#model-architecture)
  - [Data Preprocessing](#data-preprocessing)
  - [Distractor Generation](#distractor-generation)
- [Evaluation](#evaluation)
- [Results](#results)
- [Conclusion](#conclusion)

## Introduction

This project focuses on **automatically generating questions and answers** from a given context using the **T5 (Text-to-Text Transfer Transformer)** model. The system creates meaningful questions, generates correct answers, and produces challenging distractors. It is designed to improve educational tools, customer support systems, and content creation by simplifying the question-generation process.

## Research Questions

1. How can the T5 model be adapted to generate relevant and coherent questions from a given context?
2. Can distractors be generated contextually using advanced NLP techniques?
3. How well does the generated output align with the desired standards of educational tools in terms of correctness and distractor difficulty?

## Dataset

The project uses the **RACE dataset**, which consists of reading comprehension questions for middle and high school students. This dataset includes a variety of texts, short-answer questions, and multiple-choice questions that are ideal for training the T5 model.

- **Dataset**: [RACE Dataset](http://www.cs.cmu.edu/~glai1/data/race/)
- **Text Type**: Reading comprehension passages and associated questions.

## Usage

1. Clone the repository:
    ```bash
    git clone https://github.com/Afikcan/Question-Answer-Generation-from-Context.git
    cd Question-Answer-Generation-from-Context
    ```

2. Install the necessary dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Train the model on the RACE dataset:
    ```bash
    python train.py --dataset race --model t5-base
    ```

4. Generate questions:
    ```bash
    python generate_questions.py --input "path_to_text"
    ```

## Approach

### Model Architecture

The T5 model was chosen due to its strong ability to handle multiple natural language tasks, including question generation. The model converts text into a "question-answer" format, leveraging its pretrained language model to handle a variety of contexts.

### Data Preprocessing

The dataset was preprocessed to ensure that the input context, answer, and distractors were in the correct format. The **YAKE** and **BERT WSD** techniques were used for keyword extraction and disambiguation to ensure distractors were contextually relevant.

### Distractor Generation

Distractor generation involved using **BERT WSD** for word sense disambiguation to create plausible but incorrect options. This ensures that distractors are challenging yet contextually appropriate, improving the quality of generated multiple-choice questions.

## Evaluation

The performance of the model was evaluated using the **ROUGE** metric, which measures the overlap between the generated questions and reference questions.

- **ROUGE-1**: Measures unigram overlap.
- **ROUGE-2**: Measures bigram overlap.
- **ROUGE-L**: Measures the longest common subsequence.

## Results

The initial model performance showed promising results:
- **ROUGE-1 F-score**: 41.40%
- **ROUGE-2 F-score**: 24.76%
- **ROUGE-L F-score**: 40.31%

These results indicate the model's capacity to generate contextually relevant questions, but with room for improvement, particularly in generating more complex and nuanced questions.

## Conclusion

This project demonstrates the feasibility of using the T5 model for question generation in various applications. While the model performs well, further refinement is needed to enhance distractor generation and improve overall question quality. The approach provides a foundation for future advancements in automated question generation.
