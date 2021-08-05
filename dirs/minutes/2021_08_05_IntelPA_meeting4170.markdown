---
layout: page
title: 2021_08_05_IntelPA_meeting
permalink: /minutes/2021_08_05_IntelPA_meeting/
---

[**<-back**](/minutes)  

# Minutes of Intel-PA group meeting (05/08/2021, 13:00 - 14:00)
next meeting: 04/08/2021, 13:00 - 14:00

## Shortcomings of existing modules

### ASR
- Good enough for now

### Natural Language Understanding
- Need to add symptom attribute information (pain levels, location on body etc.)

### Diagnosis module
- **Need more data** - biggest concern at the moment
- Edges of the graph need to be weighted by frequency of the symptom's appearance in dataset
- No. of conversational turns taken to reach diagnosis should be reduced

### Natural Language
- Use more varied templates - maybe 5 or 6 for now

### Text to speech
- Naturalness of the Glow-TTS model is not very good - maybe use Google TTS API?
- OR use transfer learning to improve Glow-TTS pronunciation of difficult medicine-related words

### GUI
- Not important at this stage, but needs to be done by end of the year

## Action points
- Jiajun to integrate ASR module into demo
- Ruibin to research papers in order to find out how to extract attributes from a symptom phrase
- Kavi to apply weighting to the edges of the demo graph and update the scoring system to make use of this
- Xiaoxiao to look through the datasets in the [NHS data catalogue](https://ehr.wangqiru.com/dataset/) to see if we can use one or more of them in our diagnosis module