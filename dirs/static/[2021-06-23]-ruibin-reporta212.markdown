---
layout: page
title: [2021-06-23]-ruibin-report
permalink: /static/ruibin/progress/[2021-06-23]-ruibin-report/
---

[**<-back**](/static/ruibin/progress)  

## What did I do

1. Natural language understanding of patient's input
    * the essential of this part is to extract the symptom entities from the input sentence.

    * I try to extract entity of the input by myself, failed. It is difficult to label the data.  linking the oral description to the normalizational description. 

    * So I decided to use exist system, for example: Biobert and IBM Annotator for clinical data. 

    * examples of labeled sentence.

        label: cd /home/newdisk/personal_code/JointBERT/data/atis


i want to fly from    baltimore        to     dallas           round          trip

O   O   O  O   O  B-fromloc.city_name  O  B-toloc.city_name  B-round_trip   I-round_trip


2. usage of the Biobert

    * API is avaliable([Links](https://bern.korea.ac.kr/))

    * programing of visting this API has be finshed

    * model is trainable([github](https://github.com/dmis-lab/biobert-pytorch)) 

    * The training part of text classification have been finished. 

    * The shortage of this method is too rough, only have three label, BIO. 

    * It is free to use

    * debuging at the local computer has been finshed, input can get labeled output




3. usage of the IBM Annotator for clinical data

    * Purpose: extract useful information from patient's sentences. 
    * [Links](https://acd-try-it-out.mybluemix.net/preview)


    * Advantages:
        * API is avaliable

    * the programing of visting API has been finished
 
    * Disadvantages:
        * API out is in a mass, user should familiar with their related lables (for example: Insight type, Medical Code, and entity type), so thay can easily extract useful information of patient's input, which has High learning costs
    
    * [charge](https://cloud.ibm.com/catalog/services/annotator-for-clinical-data)
        * free: 3000*1000 characters
        * charge: Item = 1000 characters of input text;
          Customized instance = USD 10,000 per month;
            Up to 24,999 items = $0.12 per item;
            Up to 499,999 items = $0.10 per item;
            500,000 or more = 0.07 USD per item



## what I will do next

continue go as we planned

