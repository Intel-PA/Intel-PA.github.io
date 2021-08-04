# Minutes of Intel-PA group meeting (21/07/2021, 13:00 - 14:00)
next meeting: 04/08/2021, 13:00 - 14:00

## Points discussed

### Basic functionality demo
- Web crawling/data cleanup by Jiajun and Kavi
- NLP processing by Ruibin and Xiaoxiao 
- Edges of the graph need to be weighted according to likelihood of symptom contributing to disease
- Jian: In the future, browse literature or get data that allows a ML model to learn these weights
- Xiaoxiao: There are "disease islands" disconnected from the rest of the graph - we might need to tag and classify these
- Xiaosong: Location of symptoms need to be embedded as well

### Other
- Ruibin: Tried using distance between word embeddings to match user text to database items, but no luck
- Jian: Need to bring in a medical expert at somepoint after we have a full pipeline to advise us on symptom weights etc.

## Action points
- Implement most frequent symptoms ordering (for asking questions)
- Integrate ASR and TTS to this demo
- Apply for AWS cloud computing