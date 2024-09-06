# Question-Answer Generation from Context

## Table of Contents
- [Introduction](#introduction)
- [Motivation](#motivation)
- [Research Questions](#research-questions)
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [Model Architecture](#model-architecture)
  - [Data Preprocessing](#data-preprocessing)
  - [Distractor Generation](#distractor-generation)
- [Evaluation](#evaluation)
- [Results](#results)
- [Challenges](#challenges)
- [Conclusion](#conclusion)

## Introduction

This project focuses on creating an **automated system for generating questions and answers** from a given context using the **T5 (Text-to-Text Transfer Transformer)** model. It is designed to support educational platforms by automating the process of question generation, including distractor options for multiple-choice questions. The system has wide applications, particularly in enhancing e-learning experiences and testing systems.

## Motivation

Manual question generation for tests and educational content is time-consuming. With the advancements in Natural Language Processing (NLP), this project aims to **automate the generation of contextually relevant questions** and **generate plausible distractors** that challenge the learner without losing context relevance. By using a transformer-based model like T5, this project addresses the need for scalable question generation solutions in education and other fields.

## Research Questions

The project explores the following questions:

1. How can the T5 model be adapted to generate contextually relevant and coherent questions?
2. How can distractors be generated that are contextually appropriate yet challenging?
3. How well does the system perform in comparison to existing models in generating meaningful and usable questions?

## Dataset

This project uses the **RACE dataset** (ReAding Comprehension dataset), which includes reading comprehension texts along with questions and multiple-choice answers designed for middle and high school students. This dataset serves as a foundation for training the model to generate questions and distractors.

- **Dataset**: [RACE Dataset](http://www.cs.cmu.edu/~glai1/data/race/)
- **Text Type**: Reading comprehension passages, questions, and answers.

## Methodology

### Model Architecture

The T5 model was chosen for its flexibility in text-to-text transformations. It takes an input context and generates both a question and distractor choices. T5’s pre-trained model was fine-tuned to handle the RACE dataset, which provides the necessary context-question pairs for training.

### Data Preprocessing

Preprocessing involved cleaning the dataset, extracting key context and question-answer pairs, and formatting the data for training. Techniques like **YAKE** and **BERT WSD** were used for keyword extraction and word sense disambiguation, ensuring that distractors are contextually relevant and challenging.

### Distractor Generation

Generating plausible distractors is a key challenge in automated question generation. By using **BERT WSD**, the project disambiguates key terms from the context to create distractors that are close in meaning but incorrect, adding a layer of difficulty for the learner.

## Evaluation

The model’s performance was evaluated using the **ROUGE (Recall-Oriented Understudy for Gisting Evaluation)** metric, which measures the overlap between the generated questions and reference questions from the dataset. The ROUGE scores provide a quantitative measure of how well the generated questions and answers align with the reference questions.

- **ROUGE-1**: 43.83%
- **ROUGE-2**: 24.76%
- **ROUGE-L**: 40.31%

## Results

The system was able to generate coherent and contextually appropriate questions, with improvements seen after tuning the training process:

- The T5 model achieved **ROUGE-L scores of 40.31%**, showing that while the system is able to generate reasonable questions, there is room for improvement in generating more sophisticated and nuanced questions.
- Distractor generation proved challenging but effective, producing distractors that made multiple-choice questions more engaging.

## Challenges

1. **Distractor Generation**: Crafting relevant yet challenging distractors is one of the key complexities. Managing polysemous words using **BERT WSD** was a partial solution, but further refinement is needed.
2. **Model Training**: Due to hardware limitations, fine-tuning the T5 model faced technical hurdles such as memory limitations, which restricted the size of batches and the number of epochs used during training.

## Conclusion

This project demonstrates the potential of the T5 model in automating question-answer generation from a given context, contributing to advancements in educational technology. While the results show promise, further refinement in distractor generation and larger-scale training are needed to fully unlock the potential of automated question generation systems.
