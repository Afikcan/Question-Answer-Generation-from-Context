# Automatic Question-Answer Generation from Context
## Objective and Motivation

Our project aims to revolutionize teaching methodologies and content creation. The primary goals include generating relevant questions based on texts and creating stimulating distractors. This project addresses complex challenges related to distractor development and T5 model training.

## Model Used - T5
As previously mentioned, we utilized the T5 model.

### T5 Model Overview

T5, a transformative NLP model, operates on an encoder-decoder architecture crucial for text processing and generation.

  Encoder: Analyzes the input text, converting text into tokens to create a rich, contextualized representation of each segment. Using Transformer blocks, it performs operations like self-attention to deeply understand text nuances.

  Fully-Visible Attention Mask: Allows each word (or token) in a sequence to "see" or take into account all other words during the attention calculation, enabling the encoder to capture relationships and contexts across the entire input sequence.

  Decoder: Focuses on producing the output text, systematically constructing the output based on the encoded input for tasks like translation, summarization, or responding. It employs Transformer blocks similar to the encoder but uses cross-attention mechanisms for contextually aligned and coherent output. Additionally, the decoder uses a "causal" attention mask, ensuring words can only consider themselves and preceding words, not future ones during text generation.

## Training
We utilized RACE and SQUAD data, combining them for training. RACE data includes text, a question, four options, and the correct answer indicated by a letter (ABCD). SQUAD data has a similar structure. We merged and formatted these datasets into text, question, and correct answer format.

We used a QuestionGenerationDataset class to prepare and process textual data for a question-generation model, ensuring data is in the correct format for transformer-based machine learning models.

The T5FineTuner class handles model initialization, data processing for training, and validation. It sets up the T5 model and tokenizer with specified hyperparameters, ensuring reproducibility.

Initially, we attempted to fine-tune the base T5 model but faced limitations. Subsequently, we refined T5-small, achieving better performance with adjusted epochs, batch size, and learning rate.

## System Steps

Our system comprises three main parts: keyword extraction, question generation, and distractor generation.

### Keyword Extraction

We extract keywords from both the original and a summarized version of the text, using models like T5 for summarization and nltk for stop words removal. This process involves identifying and selecting the most significant keywords.

### Question Generation

We use the refined T5 model to generate questions based on the original text and keywords.

### Distractor Generation

We employ two methods for distractor generation: using WordNet for specific terms and sens2vec with Maximal Marginal Relevance for selecting the best distractors based on semantic similarity and diversity.
Conclusion

In the latest version of our model, most generated questions are semantically meaningful, although there are still challenges with semantic matching for distractors. Despite not achieving optimal success rates yet, the significant potential of our model is evident. Improvements are expected with more specific question type separation, enhanced datasets, or more powerful hardware for fine-tuning.
