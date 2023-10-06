# LeadQualifier

This repo is a collection of scripts we use at Xeneta to qualify sales leads with machine learning. Read more about this project in the Medium article [Boosting Sales With Machine Learning](https://soliddev09.blogspot.com/2023/10/boosting-sales-with-machine-learning.html).

Our simple scikit learn Random Forest algorithm obtain an accuracy of 86.4% on the testing data.

Read more about this project in the Medium article [Boosting Sales With Machine Learning](https://soliddev09.blogspot.com/2023/10/boosting-sales-with-machine-learning.html).

Unfortunately, we can not provide you with the raw text dataset we've used to train our algorithm, as it contains sensitive company information (who our customers are). However, we have added our own vectorized & transformed data in the /data folder (which is the final input to the RF algorithm). Feel free to play around with this data and see if you can beat our accuracy.


To run create your own lead qualifier, you'll need to run these scripts on your own customer data, which you can do using the FullContact API.

## [train_algorithm](https://github.com/ogfan/LeadQualifier/tree/master/train_algorithm)

This script trains an algorithm on your input data. It expects two excel sheet named *qualified* and *disqualified* in the [input](https://github.com/ogfan/LeadQualifier/tree/master/train_algorithm/input) folder. These sheets need to contain two columns:

1) URL
2) Description

![](https://raw.githubusercontent.com/ogfan/LeadQualifier/master/img/sheet.png)

Run the script:

    python run.py

It'll dump three files to your disc:

- algorithm
- vectorizer
- tfidf_vectorizer

Copy paste these into the 'qualify_leads/algorithms' folder, and it'll be ready to start predicting.

## [qualify_leads](https://github.com/ogfan/LeadQualifier/tree/master/qualify_leads)

This is the script that actually predicts the quality of your leads. Add an excel sheet named 'data' in the '/input' folder. Use the same format as the example file that's already there.

Run the script:

    python run.py

Got questions? Email me at soliddev09@gmail.com.