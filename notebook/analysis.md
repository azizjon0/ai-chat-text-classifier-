Data Structure
(images/Group_(1).png)
The dataset contains 1,500 messages. They represent a combination of scripted and AI-generated responses. Here is a brief visualization and some interesting statistics:
1.	We have 9 columns (for us programmers, 0 is also a number and is usually the first one). We will use some of the columns, specifically those related to categories and chats between the user and AI.
2.	We have 1,359 chats. This is not much, but we can allocate 80% for training and 20% for model testing.
3.	The data is complete (there are no empty columns, as is often the case with incomplete data).
4.	We can see that the final columns do not present any issues, indicating that the data is evenly and correctly filled. Also, I noticed that the data was collected over a short period, judging by the time column.
Goal
From this data, we need to build a machine capable of accurately categorizing messages. The machine should be fast enough for Japeto to use categorization in real-time.
3	Data Analysis                   
 
Tasks
Categories 
Determine the number of categories and make sure the classes are balanced.
Common words and phrases
Identify the most frequently used words and phrases in each category.
Category Intersection 
Analyse category intersection - identify words and phrases that are repeated in multiple categories.
Message Length and Complexity
Assess message length and complexity. The word/character count ratio is examined.

Category Distribution in the Dataset 
The dataset contains various categories, but some appear significantly more frequently than others.
For example, "General conversation" and "Services" often occur together.
Some categories may be too rare, which could cause issues when training the model.








Word Cloud for User Messages
 
The dataset contains various categories, but some appear significantly more frequently than others.
User messages often contain simple requests (e.g., greetings, questions about functionality).
For example, "General conversation" and "Services" often occur together.
The chatbot responds with both neutral and specific replies, depending on the category.
Some categories may be too rare, which could cause issues when training the model.



Visualisation 
 The histogram plot shows the distribution of the length of user messages (in blue) and chatbot answers (in red). The X-axis shows the length of messages in characters, the Y-axis shows the frequency (the number of messages of a certain length).
Conclusion 
If a category contains many short words, the classification model may erroneously assign any short message to it, even if it is not relevant to the essence of the category. This can lead to a bias in the model's predictions. Therefore, it is essential to consider the length of messages as a factor that may affect the quality of classification.
 
A model restricted to selecting only one category may misinterpret the context. Therefore, a logical solution is to use multi-label classification, where a single message can be classified into several categories.
Preparing Data                                        
 Convert category labels (e.g., “Support”, ‘Billing’, “Reviews”) to numeric values (e.g., 0, 1, 2).
This is necessary because the model works with numbers, not strings.
Feature engineering
Feature engineering is the process of selecting, manipulating and transforming raw data into features that can be used in supervised learning.

 Converts the text of a user_message message into a number of TF-IDF attributes.
TF-IDF (Term Frequency-Inverse Document Frequency) measures how important a word in a message is relative to all messages.
max_features=5000 limits the vocabulary to 5000.
stop_words="english" removes common words such as "is", "the", "in" and parasite words.
ngram_range=(1, 2) includes both single words (unigrams) and pairs of words (bigrams).



Balancing Classes with Oversampling
 Solves the problem of class imbalance (when some categories occur much more often than others).
RandomOverSampler creates duplicate examples from minority classes so that all classes have the same number of examples.
This helps prevent the model from biasing towards majority classes.
Train-Test Split
 Splits the data into training (80%) and test (20%) sets.
This allows training the model on one part and evaluating it on another, unseen part. random_state=42 ensures repeatability (same partitioning every time)
