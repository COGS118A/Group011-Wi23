DATASET 1:
Dataset used
The data source used for this project is LIAR dataset which contains 3 files with .tsv format for test, train and validation. Below is some description about the data files used for this project.

LIAR: A BENCHMARK DATASET FOR FAKE NEWS DETECTION

William Yang Wang, "Liar, Liar Pants on Fire": A New Benchmark Dataset for Fake News Detection, to appear in Proceedings of the 55th Annual Meeting of the Association for Computational Linguistics (ACL 2017), short paper, Vancouver, BC, Canada, July 30-August 4, ACL.

original dataset contained 13 variables/columns for train, test and validation sets as follows:

Column 1: the ID of the statement ([ID].json).
Column 2: the label. 
(Label class contains: True, Mostly-true, Half-true, Barely-true, FALSE, Pants-fire)
Column 3: the statement.
Column 4: the subject(s).
Column 5: the speaker.
Column 6: the speaker's job title.
Column 7: the state info.
Column 8: the party affiliation.
: For Column 3 to 8, they are all discrete variables, so we didn’t consider to train this variables
Column 9-13: the total credit history count, including the current statement.
Column 9: barely true counts.
Column 10: false counts.
Column 11: half true counts.
Column 12: mostly true counts.
Column 13: pants on fire counts.
Column 14: the context (venue / location of the speech or statement).
To make things simple we have chosen only 2 variables from this original dataset for this classification. The other variables can be added later to add some more complexity and enhance the features.

Below are the columns used to create 3 datasets that have been in used in this project

Column 1: Statement (News headline or text).
Column 2: Label (Label class contains: True, False)
You will see that newly created dataset has only 2 classes as compared to 6 from original classes. Below is method used for reducing the number of classes.

Original — 	New
True — 		True
Mostly-true —  True
Half-true — 	 True
Barely-true —   False
False —		False
Pants-fire —	False

The dataset used for this project were in csv format named train.csv, test.csv and valid.csv and can be found in repo. The original datasets are in "liar" folder in tsv format.



DATASET 2:
politifact_fake.csv - Samples related to fake news collected from PolitiFact
politifact_real.csv - Samples related to real news collected from PolitiFact
gossipcop_fake.csv - Samples related to fake news collected from GossipCop
gossipcop_real.csv - Samples related to real news collected from GossipCop
Each of the above CSV files is comma separated file and have the following columns

id - Unique identifider for each news
url - Url of the article from web that published that news
title - Title of the news article
tweet_ids - Tweet ids of tweets sharing the news. This field is list of tweet ids separated by tab.


LIAR dataset and the politifact and gossipcop datasets all contain information related to news and its veracity. They can be combined to create a larger dataset that can be used for training models to detect fake news. Use one dataset to validate the other: two datasets contain different types of information, they can be used to validate each other: LIAR dataset can be used to validate the performance of models trained on the politifact and gossipcop datasets, and vice versa. We can use one dataset for feature engineering:The politifact and gossipcop datasets can be used to extract features related to the sources of news articles, which can be used to train models on the LIAR dataset. Also, this shows using ensemble methods: Ensemble methods combine the predictions of multiple models to improve accuracy. By training models on both datasets and using ensemble methods, the overall performance of the model can be improved. In summary, combining datasets, using one dataset for feature engineering, and using ensemble methods can all be effective ways to use our two datasets. The most effective approach will depend on the specific research question and the nature of the data. It is important to note that using a model trained on one dataset to predict labels on another dataset may result in decreased performance due to differences in the data distributions.
