---
layout: page
title: 2021_11_22_IntelPA_meeting
permalink: /minutes/2021_11_22_IntelPA_meeting/
---

[**<-back**](/minutes)  

# Minutes of Intel-PA student meeting (22/11/2021, 14:00 - 15:00)


## Points discussed
* Scope of the project - Current scope is too broad, as is general cancer diagnosis. Need to focus on a narrower area. However, the availability of data is lower in this case, so we need to find a suitable dataset. 

* Options going forward - one of these needs to be picked depending on what dataset is found: 
	* Triage system of common diseases
	* Referral system for a specific disease

* AI cluster manager:
	* Cannot use VGPUs - only available on select cards + need an expensive license
	* Kubernetes - overkill for this project
	* SLURM - very basic task scheduler, no containerisation out of the box, we'd need to write all this logic ourselves
	* Determined.ai - Should be easy to set up and run, and has many ML features built in. This is the tool we are currently thinking of using. 

## Todos
* Kavi: Sign up with Infermedica and use their API, find diagnostic criteria for disease referral

* Jiajun: Liaise with Russell (about temporary PCs) and try to set up determined.ai cluster on these machines 

* Everyone: Find a dataset that includes dialogue between doctor and patient

