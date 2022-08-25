---
layout: page
title: 2022_08_25_NLP_progress_meeting
permalink: /minutes/2022_08_25_NLP_progress_meeting/
---

[**<-back**](/minutes)  

# Minutes of catch-up with NLP group - 25/08/2022

## Xiaoxiao
- Trained GPT-2 with sentences from medical articles. These were not bits of dialogue between patients and doctors. Results were not satisfactory
- Reading a paper about 0 shot learning - https://arxiv.org/pdf/2111.01998.pdf
- relevance to intelPA: use this framework to take in highly structured prompts and output questions in natural language

## Rehman
- Working on a decision tree architecture for conversation structure 
  - Entity recognition is difficult - needs to be hard-coded (tried gpt2 but doesn't work well) 
  - Current problem is one of "entailment" - this refers to the meaning behind a natural language sentence. Rehman believes that large, popular embedding systems such as GPT suffer from biases that make entailment difficult. He is working on a "self-contained" embedding system to encode sentences. This system would be trained on much smaller datasets, the biases of which can be accounted for more easily.
- Completed age extraction module (can infer patient's age from a natural-language sentence)
- Completed affirmative/negative recognition module (can figure out if a patient's natural language utterance means yes or no)

## Huan
- Made template from clinical observations at Dr. Skene's clinic
- Trying to increase size of the dataset - data consists of conversation text between doctor and patient. Her approach is to augment it using Machine Learning tools for paraphrasing

## Action points
- Rehman to complete time duration calculation module. This module is responsible for returning a length of time (in days? weeks?) given a natural language description, e.g "two weeks ago", "Since 1955", "a year and a half" etc.
- Xiaoxiao to meet with Julia and talk about how to continue - possibility of using a subset of the sentences from the medical articles (maybe just lines that contain questions?). 
