# Clinical_Trials_Unsupervised

### My methodology:

#### Data collection:
I collected data from the following subreddits: r/AskDocs, r/healthcare, r/medicine, r/clinicaltrials and r/clinicalresearch, wherein I saved post titles, post descriptions and comments. In order to maintain privacy, I opted not to save the profile names at this point. However, as I mentioned in my notebook present in notebook/models.ipynb, this could be an addition in the future, subject to any privacy and ethical norms.

#### Model training
I used huggingface's pre-trained BERT as the model and fine tuned it on the collected data, which gave me a model that was not too robust. 

#### ChatBot:
I used LangChain with OpenAI's GPT3.5 in order to train GPT on the collected data, which can generate messages.

### Ethical considerations:
As I only used public data currently available, I think that there is no consideration of breach of privacy or otherwise. However, if in the future, a DM is sent to a Reddit user, the chat must remain private and cannot be used to train AI, unless authorized by the Reddit user.