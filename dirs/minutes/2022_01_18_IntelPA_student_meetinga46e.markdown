---
layout: page
title: 2022_01_18_IntelPA_student_meeting
permalink: /minutes/2022_01_18_IntelPA_student_meeting/
---

[**<-back**](/minutes)  

# Minutes of Intel-PA student meeting (18/01/2022, 14:00 - 15:15)

## Points discussed

### Discuss information learned from Thursday's clinical observation

General Pattern of Consultation:
* specific issue that brought you here ("tell me your story")
* past medical history
    * breast related
    * general(major diseases/operations/implants etc......)
* family history
* hormone & medications
* alcohol, smoking & substances

Regarding GP Reference Form: doctors tend to just focus on the list of checkboxes on the first page

Decided Architecture: start with a general list of questions, then explore based on answers.

Note: kari got a colleague at Oxford working on the similiar consultation problem, but via telephone
they are using a mix of models(including BERT) and try to just fine-tune the layers close to output 
try huggingface if you need BERT related stuff......

### Decide on a central data structure for the chatbot

Presenting to doctors:
* text + hightlight
* graph?
* "augmented text": points extracted and highlight sources in recorded dialogue when requested

Ask doctors for feedback!

internal: deferred to NLP guys, figure out later


### Make a priority list of features that need to be implemented

todo:
* Interfaces for the doctors (Q&A+hightlighting)
* get an existing chatbot running as the core model & focus on the interaction side of things as we have IBM extractor already

explore:
* get facial animation working
* try out different TTS model

dataset: 
* (consensus) collecting from clinic is not feasible, try to get general conversation related dataset instead
* general extractor + manual heuristics

milestone: internal datastructure & architecture design presentation

### Assign implementation of these features to various team members

* jiajun & kavi: doctor-side GUI
* rehman, kari & xiaoxiao: pick a chatbot to use & internal data structure design

* Jiajun: animation
* kavi: TTS

### Discuss availability for helping out with multimodal data capture (Potentially Monday 24?)
* jiajun & kavi are going

### Decide if we want to go to this NHS AI conference in London
* do risk assessment, agree from supervisor & expenses with zoe if you want to go

note:
* do risk assessment for next visit to the clinic!

## Action points

* kavi & jiajun: doctor-side GUI
* rehman, kari & xiaoxiao: internal datastructure design & existing chatbot selection