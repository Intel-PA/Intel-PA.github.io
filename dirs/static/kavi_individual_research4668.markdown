---
layout: page
title: kavi_individual_research
permalink: /static/kavi/progress/kavi_individual_research/
---

[**<-back**](/static/kavi/progress)  

# Kavi: Topic - emotional classification of patient

Part of what will make Intel-PA an empathetic conversation partner will be its ability to react to the emotional state of the user. 

To accomplish this, I propose a multi-modal paralinguistic emotion detection system at the very front of the system. This system will be responsible for taking in the streamed video feed from our client webapp and determine the emotional state of the patient by analysing the paralinguistic cues\* in the video. The rest of the system can then use the downstream information from this module to make decisions on how best to match the user's emotional state. This could for example involve instructing the Natural Language generation module to generate sentences that are more reassuring and calming.

My research in this area will involve investigating the application of the Multimodal Bottleneck Transformer (MBT) [1] to the problem of emotion detection. This is a newly developed audiovisual fusion technique based on the transformer architecture and has shown to be very effective at integrating these two modalities.

However, in the interest of getting a prototype working as fast as possible, I plan on integrating a freely available [facial emotion detection system called DeepFace](https://github.com/serengil/deepface). This only works on images, so we will have to periodically poll Jiajun's video feed and send the frames to the API. Preliminary testing shows that the service is able to analyse an image for emotion in about 200ms, so the maximum polling frequency is 5Hz, although in practice it will have to be less in order to account for network delays and provide a smooth user experience. This solution has the drawback of being unimodal (video only), but will be replaced in the future with the multimodal (audio and video) model that will be developed over the course of my research. 
 

In summary, my objectives are:
* Identify a suitable off-the-shelf emotional recogntion service [done]
* Verify its functionality [done]
* Integrate with rest of IntelPA codebase
	* Create dummy video stream so that the logic of the emotion detection system can be worked out and implemented
	* Poll video \~5x every second and extract frames to process 
	* Create interface for rest of the sub-modules to access facial emotion data



\* Paralinguistic signals are visual and audio cues that make up a large proportion of the information conveyed in human communication [2]. They add extra meaning to the semantics, or the plain text of the speech and are often used to remove ambiguities in what was said. 



### References
[1] Arsha Nagrani et al. ‘Attention Bottlenecks for Multimodal Fusion’. In: (2021). arXiv: 2107.00135. url: http://arxiv.org/abs/2107.00135 (visited on 24/02/2022)
[2] Michal Ephratt. ‘Linguistic, paralinguistic and extralinguistic speech and silence’. en. In: Journal of Pragmatics. Silence as a Pragmatic Phenomenon 43.9 (July 2011), pp. 2286–2307. url: https://www.sciencedirect.com/science/article/pii/S0378216611000853 (visited on 29/06/2022)
