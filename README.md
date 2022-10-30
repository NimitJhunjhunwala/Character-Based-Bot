# Character-Based-Bot
A peronality based chatbot that talks like your favourite character. The repositority to refer the model is on Hugging Face. Click [here](https://huggingface.co/Nimit-Jjw/DialoGPT-chandler-penny?text=Hey+my+name+is+Mariama%21+How+are+you%3F) to view the repository.
<div align = "justify">
<p>Chatbot personality defines the user experience. You can think of Alexa or Siri, for example. Their personalities are key to the way users interact with their services. The jokes, sarcasm, and the way they handle complex conversation are all integral to their success as artificially intelligent assistants. We are aiming to make our chatbot unique by assigning a personality to it. </p>

In 2014, the sequence to sequence model being used for translation opened the possibility of phrasing dialogues as a translation problem: translating from an utterance to its response. The systems built using this principle, while conversing fairly fluently, aren’t very convincing because of their lack of personality and inconsistent persona. In this project, we experiment building open-domain response generators with personality and identity. We built a chatbot that imitates Chandler and Penny, the popular TV show character from FRIENDS and Big Bang Theory respectively. A successful model of this kind can have a lot of applications, such as allowing people to speak with their favourite celebrities, creating more life-like AI assistants, or creating virtual alter-egos of ourselves. The model was trained end-to-end without any hand-crafted rules. The bots talk reasonably fluently, have distinct personalities, and seem to have learned certain aspects of their identity.

### Dataset Details
[Dataset 1: FRIENDS](https://www.kaggle.com/datasets/blessondensil294/friends-tv-series-screenplay-script)<br>
This Dataset contains the text file of all the Screenplay Scripts and Dialogue for each episode in the FRIENDS TV Show.<br>
Dataset Preview:
 
![FRIENDS dataset preview](https://github.com/NimitJhunjhunwala/Character-Based-Bot/blob/main/FRIENDS%20dataset%20preview.png)

[Dataset 2: Big Bang Theory](https://www.kaggle.com/datasets/mitramir5/the-big-bang-theory-series-transcript)<br>
The dataset consists of three columns dedicated to: the episode number/ season, actor/scene, and the dialoge they utter.<br>
Dataset Preview:

![BBT dataset preview](https://github.com/NimitJhunjhunwala/Character-Based-Bot/blob/main/BBT%20dataset%20preview.png)

### Model Details
The model used to train the chatbot was the DialoGPT model. DialoGPT is a large-scale pre-trained dialogue response generation model for multi-turn conversations. The model is trained on 147M multi-turn dialogues from Reddit discussion threads. You can refer to the official docs [here](https://huggingface.co/docs/transformers/model_doc/dialogpt).

### Processing Details
After performing a sequence of preprocessing steps using techniques like string matching and regular expressions, we end up with a new dataframe that is stored as a CSV file for future usage. <br>
A snippet of the dataframe is shown below:
 
![preprocessed dataframe snippet](https://github.com/NimitJhunjhunwala/Character-Based-Bot/blob/main/preprocessed%20dataframe%20snippet.png)

Finally, we create a context dataframe (discourse analysis) that has for every dialogue spoken by the target character, n number of dialogues leading up to it as the features. An example is shown below:

 ![context dataframe](https://github.com/NimitJhunjhunwala/Character-Based-Bot/blob/main/context%20dataframe.png)

### Output
The bot was able to successfully carry out simple conversations. The example below shows the same.

>> User:Hello!<br>
BOT: Hello! :D<br>
>> User:How are you?<br>
BOT: Good! How are you?<br>
>> User:I am also good. Do you like the weather today?<br>
BOT: It's beautiful here!<br>
>> User:Should we go out for a walk?<br>
BOT: Yes! I'm excited to go out<br>

As the queries start getting more and more complex, the bot’s performance does flutter a bit, but it still is able to pick up basic references, like the name of a person. It also starts to pick up on character’s preferences like their favourite colour, etc.

>> User:Hey chandler!<br>
BOT: Hey, how's it going?<br>
>> User:Good, did you see Joey today?<br>
BOT: Yeah, he's awesome!<br>
>> User:What is your name?<br>
BOT: His name is Joey.<br>
>> User:Good to hear! Will catch up with you later.<br>
BOT: No worries. I'll be around for a while now.<br>
>> User:What is your favorite color?<br>
BOT: Blue. Or red.<br>
>> User:How do you feel about going to the gym?<br>
BOT: I'm not sure. I'm not a gym person.<br>
>> User:Bye!<br>
BOT: Byeee!<br>

The model was also evaluated using the perplexity metric. The perplexity metric in NLP is a way to capture the degree of ‘uncertainty’ a model has in predicting (i.e. assigning probabilities to) text. The perplexity of our model came out to be 0.75, which is a really good value for a conversational chatbot. 

### Issues to solve
•	The padding error in between the conversation.
   
   ![issues to solve](https://github.com/NimitJhunjhunwala/Character-Based-Bot/blob/main/issue%20to%20solve.png)

</div>
