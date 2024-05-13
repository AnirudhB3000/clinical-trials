# Clinical_Trials_Unsupervised

### My methodology:

#### Data collection:
For more details navigate to notebook/Models.ipynb

To keep the data relevant, I limited my search to: r/AskDocs, r/healthcare, r/medicine, r/clinicaltrials and r/clinicalresearch. Using the praw library and Reddit's API, I saved the top 100 posts, their top 100 relevant comments and the usernames of the posters. As I am limited by Reddit's API T&Cs, I could only scrape 477 documents.

#### Model training
I used HuggingFace and PyTorch to train the model. I first cleaned the texts by removing whitespace, punctuation and other irrelevant data and then tokenized it with padding limited lengths to 512. I then passed it to the BERT-Based-Uncased pretrained model.

##### My motivation for using a pre trained model:
The data that I have is limited. HuggingFace's pre trained BERT models have been trained on a large number of English words, thus it improves the robustness of the current model.

I fine tuned the model using the unsupervised data from my collection and created the sentiment analyzer. 

#### ChatBot:
I used LangChain with OpenAI's GPT3.5 in order to train GPT on the collected data, which can generate messages. I included a field to ensure whether the recorded conversations persist or not-whether the messages can stay in memeory or not.

### Ethical considerations:
As I only used public data currently available, I think that there is no consideration of breach of privacy or otherwise. However, if in the future, a DM is sent to a Reddit user, the chat must remain private and cannot be used to train AI, unless authorized by the Reddit user.

### Future implementation:

#### Sentiment analyzer: 
I would create a pandas datafram and assign a sentiment to the users and then send them messages using the ChatBot. As for the model, I would fine tune it on labelled data, which I could get using Scale AI's Data Engine.

#### ChatBot:
I would probably fine tune it on exclusively a singular opinion, as it could hallucinate if it learns the entire corpus.

# How to run
Clone/Download the repository to your local device.

Install Python3

Run 
```
pip install -r requirements.txt
```

A virtual environement is not necessary but recommended.

To see the data collection and model building, navigate to notebook/Models.ipynb and click Run -> Run all

The updated model.pth will be saved to the folder models.

To run the chatbot, run the following command in your terminal:
```
python chatter.py "<Your query here>"
```