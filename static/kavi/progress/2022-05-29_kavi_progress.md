# Progress report - 05/04/2022 - Kavi

## What I've done

* Helped Jiajun change the deployment method of the Intel-PA application. It is no longer hosted on Heroku, but on a machine in the BU network.  
* Got results from audio augmentation experiments, searching for conferences to submit to.
* Reviewed 2 papers for CGI 2022
* Co-authored a paper with Ruibin and submitted to CASA 2022. My contribution was to help him integrate his language model with the Intel-PA codebase.
* Finished writing major review and submitted it - arranged the examination for the 9th of June
* Found large multimodal emotionally labelled dataset: [CMU-MOSEI](http://multicomp.cs.cmu.edu/resources/cmu-mosei-dataset/), which I will use to combine both audio and visual modalities in training. 
* Implemented the Vision transformer architecture (benefits over CNNs include better performace on various image datasets and much less resource intensive) to solve the problem of emotional audio classification. This will be combined with the method presented in a [recent multimodal classification paper](https://arxiv.org/abs/2107.00135) to genreate a model capable of using multimodal data to predict emotion from both video and audio. Down the line, this will form part of Intel-PA's input system in recognising a user's emotion so it can be responded to appropriately by the rest of the system


## What I'll do next

* Find a more suitable character model asset for the 3d avatar - current one is a bit too unprofessional
* Prepare for the major review by creating a presentation and revising the material submitted in the review documentation
* Write dataset code to process the CMU-MOSEI dataset. It is a large audiovisual dataset of around 117GB and needs preprocessing to be used as input to the vision transformer,