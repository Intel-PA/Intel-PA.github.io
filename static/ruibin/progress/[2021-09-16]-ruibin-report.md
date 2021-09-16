## What did I do

1. assist Prof. Yang to finish two surveys:

    *  [[A Survey of the UK Film](https://github.com/Intel-PA/Intel-PA.github.io/blob/jekyll-site/static/ruibin/progress/A%20Survey%20of%20the%20UK%20Film.md)]

    * [[Remote Virtual Production Survey](https://github.com/Intel-PA/Intel-PA.github.io/blob/jekyll-site/static/ruibin/progress/Remote%20Virtual%20Production%20Survey.md)]


2. coding of the Sentiment Analysis part for our project[[code](https://github.com/swjtuRobin/GPT2)]

    * classification task
    
    * use the IMDB Dataset

        IMDB Reviews Dataset is a large movie review dataset collected and prepared by Andrew L. Maas from the popular movie rating service, IMDB. The IMDB Reviews dataset is used for binary sentiment classification, whether a review is positive or negative. It contains 25,000 movie reviews for training and 25,000 for testing. All these 50,000 reviews are labeled data that may be used for supervised deep learning. Besides, there is an additional 50,000 unlabeled reviews that we will not use in this case study. In this case study, we will only use the training dataset.
    
    * BERT model, fine-tuning

    * Examples:

        Input: 'I don't think I have this symptom'
        
        Output: Negtive
        
        Input: 'I think so'

        Output: Positive

3. work with xiaoxiao on the AMBOSS Data Processing [[weblink](https://www.amboss.com/us/knowledge/index)]

    * [AMBOSS_disease_data.json](https://drive.google.com/file/d/1viZq98nelLf6FbiLYCNY-PldBjbmSd9y/view)

    * contains 1021 diseases and relevant information (clinal features, treatment, etiology, summary, etc.)

    * 3 meetings with Xiaoxiao on processing this dataset

    * A rough thought on "how to use this AMBOSS Data

        * the system using this dataset can be located as a diagnose tool for GP, not for patients, because the description of its clinical feature is too professional

        * shortage of our system at this stage: all the symtems are in the same level.

        * advantage of this dataset:

            1. framework of this website is well organised, structured, easy to crawl 
            2. Clinical feature can be directly used to be as a agent's question to ask. for examples

            [Acute pancreatitis](https://www.amboss.com/us/knowledge/Acute_pancreatitis/) 

            clinical feature include:

                Constant, severe epigastric pain 

                    Classically radiating towards the back
                    Worse after meals and when supine
                    Improves on leaning forwards
                
                Nausea, vomiting
                Fever
                If pulmonary complications are present: chest pain, dyspnea

         
    

## what I will do next

read papers about the application of knowledge graph on the medical field.



## Reference
