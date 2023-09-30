# Reddit-NLP

A project looking at two subreddits to see the similarities about asking for dating advice and cooking recipes.

Problem Statement
I was hired by a dating app company to look at an upcoming partnership with a food delivery app to see if they should create a colloboration event to see if people were just hungry for love or lunch. This gave me task of gathering some data from two popular subreddits, "askculinary" and "askdating" to look at the verbage used between both and to create a model that will help differentiate between love or food!

About the API
In 2023, Reddit proposed and underwent a series of changes to its API that greatly affected the ways that users, developers, and academics interact with and access the troves of data that its community freely creates.

While the cost of data storage cannot be ignored, the monetization of its API has led to a shutdown of massively popular third-party and stifled important research in the social sciences (community formation/network analysis, hate speech, discourse analysis, etc.), cybersecurity (bot detection), and—importantly for us this week—the very large and diverse world of natural language processing (semantic analysis, translation, topic modeling, disambiguation, relationship extraction, etc).

While APIs like Pushshift that collected and stored Reddit's data from its inception are no longer accessible, we can still retrieve a limited amount of data directly from Reddit's API. As with anytime you begin interacting with a new tool, you should familiarize yourself as much as possible with the documentation.

We will do a walkthrough of how to access and submit a simple request to the Reddit API together.

Project Notebook Walkthrough.
The project is composed of a total of 3 files and a presentation.
Code
This file will contain a total of 3 notebooks.

The first one will go over how I pulled the data from the reddit api and then converted them into csv files.
The second, will go into the preliminary cleaning and EDA for the project looking at the top words in both subreddits as well as getting more insight on text length and word counts. Leaving the final notebook to go over the final cleaning, EDA, preprocessing, and modeling with the combined subreddits.
The third, will go into the final cleaning, EDA, preprocessing, and modeling with the combined subreddits.
Data Collection Days
This one will house all of the csv files that were gathered from the reddit API.
Images
This will contain images from the project that will be used for my presentation.
Conclusion
Out of all the models used for the problem statement the best results were provided by my Logistic Regression model boasting a 89.5% testing score. Giving me a pretty firm model in terms of seeing if you were asking for culinary advice or dating advice. In terms of just searching by solo words, the model works even better, but my main aim was to look at the phrases shared in each. By applying bigrams, the models had a harder time predicting what reddit the post was coming from. Coupled with the removal of key words from both subreddits we came to an even more balanced model, giving better insight on what may be leading into the differences between the two. This left me to use the other models to inference details about the way my problem statement was behaving.

The KNN model showed that we did not follow a Bernoulli distribution and that our observations were not indepent of the other. This gave us a poor test score at 63.7% with a large overfitting on the training data. Sadly, the next model focusing on decision trees did not fair much better. With a gini score of 46.8%, we could see that almost half the time our decision tree would be missclassifying the next prediction. This led to an overfit model until we added the hyperparameters to control the overfitting. Once the hyperparameters were in place we no longer had an overfit model with both train and test scores placing at 62.5%, which ended up being right at our baseline point. This meant that tuning depth, splits, and sample data would effect the results of the model dramatically. Leaving us with the final two models I ran being bagging and AdaBoosting.

Both of the bagging and boosting methods worked better for the project at hand. Bagging providing the better results after a gridsearch adding 50 trees at, 86.4%. This would make sense since our decision tree seemed to grow accustomed to some irregualr patterns from the overfitting of the training set. By adding more exposure to the trees by introducing sub-samples of the training set, we ended up with a better accuracy for our testing model. This gave us a good contrast in terms of then viewing boostings scores. The boosted test scores after running a gridsearch were, 74.3% causing quite a gap to be viewed between the two. This meant that the repeated weighing of weak learners to increase influence over the model was not effective. Giving us a good idea that our model learns better through recognizing pattern recognition instead of emphasizing value on seperate sections.

I would recommend that the acquisition of more data and the time to run more modeling would help the project immensely. For future testing and exploration of the subject, having a more balanced data set would be ideal to avoid overfitting. I would also recommend that since there are quite a few relationships in the phrases used in both subreddits that we should add a few more stop words to the final operating models.
