# Minutes of meetings with NLP group - 05/09/2022

PGRs: Rehman, Xiaoxiao, Huan

Supervisors: Jian Jun Zhang, Xiaosong Yang, Jian Chang

## Discussion Points

- Rehman demoed the current bot and it's design platform. [2022-09-05-bot_design_](../static/arehman/2022-09-05-bot_design_.png).

- Current version of the bot is based on the dialogue decision tree that was provided by Dr. Tony.
- Bot can extract some of the critical information for decision nodes such as names, age, yes or no affirmation, time duration, left or right and family relations.
- In case when it fails to extract critical information then we can add a fallback node that asks the user to input the information again.

- We discussed about incorporating the intent-detection so that a corresponding tree node can be triggered based on what the user is saying. 

- Intent detection is also key in detecting OOS (out-of-scope) prompts which will then trigger the general chitchat module to generate an appropriate response.


## Suggestions

- Improve the fail-safe by adding more fallback nodes so that it can be more redundant in extracting the useful information.
- Speech recognition is not as accurate as expected. We should test it on better mic or a different Speech recognition toolkit.
- Improve on the entity extraction. Such as improve the detection of "dad's mom" as a compounded relation.
- Make sure that other parts that are planed in the future (intent-detection and small talk) will be easily portable to the current setup.

## Action points

- Make sure all the fallback nodes are added to the tree.

- Integrate the NLP module with the animation module to prepare for the Demo.

- Arrange a meeting with Dr Tony.

- Huan Xu is working on intent detection on a test dataset and meanwhile looking to create/generate our own small test dataset based on what patients usually say.

- Xiaxiao will read papers on holistic chitchat bots that use known profile information of the user and previous chat history to generate small talk.
