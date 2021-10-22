# Progress report - 21/10/2021 - Kavi

## What I've done

- Ported the GUI to a webapp for easier distribution (speech input feature missing, but all others functional)
	- Hosted for free on Heroku, which doesn't have very reliable servers at that price level. Server shuts down after 30min without activity 
- Switched the application's speech output to Microsoft's Azure platform. More natural sounding and seems to be a good choice economically: 
	- Without paid subscription, it is limited to 5M characters per month for TTS - Average conversation (start to diagnosis result) with chatbot generates \~400 characters that need to be turned to speech. This translates to 12.5k diagnoses per month within the free price tier
- Investigated facial animations for the avatar. The Azure platform provides viseme information along with TTS audio. These could be mapped to keyframes/blendshapes in order to get a crude animation working. Unsure how feasible this is within a week
- Webapp is online and can be visited [--> here <--](http://intelpa.herokuapp.com/)

## What I'll do next

- Help with any tasks related to polishing up the software before the demo on 3 Nov