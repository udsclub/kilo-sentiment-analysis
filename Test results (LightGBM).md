# Sentiment analysis
#### Datasets used: http://jmcauley.ucsd.edu/data/amazon/links.html

## Base parameters
### TfidfVectorizer:
#### max_df=0.75, min_df=3, ngram_range=(1, 3), max_features=35000, stop_words=None
### model parameters:
#### colsample_bytree=0.7, learning_rate=0.15, max_depth=-1, min_child_samples=15, n_estimators=200, num_leaves=127, reg_lambda=1, scale_pos_weight=1, subsample_for_bin=5000

###  Dataset names:
#####    train - Movie and TV 5 train sample (stratified split on 90% Train and 10% validation)
#####    test - Movie and TV 5 test sample (131041 pos / 21219 neg)
#####    polarityRT - Test_RT_polarity (5330 pos / 5330 neg)
#####    RT - reviews_rt_all (64658 pos / 37952 neg)
#####    IMDB - imdb_small (25k pos / 25k neg)

### 1. Check learning curve (initial balance)
### Imbalanced data (initial balance, about 1:5 neg/pos)

|Random state| size | TfidfVectorizer | accuracy val | f1 val|accuracy test | f1 test|acc_polarityRT|f1_polarityRT|acc RT|f1 RT|acc IMDB|f1 IMDB|
|:------------|:----|:--------------:|:-------------:|:------:|:------------:|:------:|:------------:|:-----------:|:-----:|:---:|:-------:|:------:|
|42 |20000|no stop_words|0.9105|0.60|0.9145|0.62|0.5696|0.29|0.6731|0.31|0.7743|0.72|
|42 |100000|no stop_words|0.9305|0.71|0.9386|0.75|0.6034|0.38|0.6759|0.32|0.8458|0.82|
|42 |200000|no stop_words|0.9409|0.76|0.9444|0.78|0.6097|0.39|0.7023|0.39|0.8620|0.85|
|42 |500000|no stop_words|0.9481|0.80|0.9482|0.80|0.6111|0.39|0.7027|0.38|0.8664|0.85|
|42 |1000000|no stop_words|0.9478|0.80|0.9499|0.81|0.6165|0.40|0.7066|0.39|0.8746|0.86|
|42 |1343971(all)|no stop_words|0.9491|0.80|0.9501|0.81|0.6147|0.40|0.7045|0.38|0.8747|0.87|

### 1.2 Check learning curve (balanced)
### Balanced data (50/50)

|Random state| size | TfidfVectorizer | accuracy train | f1 train|accuracy test | f1 test|acc_polarityRT|f1_polarityRT|acc RT|f1 RT|acc IMDB|f1 IMDB|
|:------------|:----|:--------------:|:-------------:|:------:|:------------:|:------:|:------------:|:-----------:|:-----:|:---:|:-------:|:------:|
|42|20000|no stop_words|0.8498|0.85|0.8407|0.60|0.6454|0.51|0.7112|0.48|0.821|0.84|
|42|100000|no stop_words|0.9048|0.89|0.9057|0.73|0.7165|0.70|0.7229|0.63|0.8896|0.89|
|42|200000|no stop_words|0.9103|0.91|0.9132|0.75|0.7286|0.71|0.7323|0.64|0.8968|0.90|
|42|370820|no stop_words|0.9151|0.92|0.9170|0.75|0.7350|0.72|0.7377|0.65|0.9011|0.90|

### 3. Check learning curve (moving balance)
### Imbalanced data (1:1, ... 1:5)
##### 50000 negative sample + 50000 * x positive,  x є [1, 1.5, 2.5, 5]

|Random state| size | TfidfVectorizer | accuracy train | f1 train|accuracy test | f1 test|acc_polarityRT|f1_polarityRT|acc RT|f1 RT|acc IMDB|f1 IMDB|
|:------------|:----|:--------------:|:-------------:|:------:|:------------:|:------:|:------------:|:-----------:|:-----:|:---:|:-------:|:------:|
|42|100000(1:1.0)|no stop_words|0.9048|0.90|0.9057|0.73|0.7165|0.70|0.7229|0.63|0.8896|0.89|
|42|125000(1:1.5)|no stop_words|0.9089|0.89|0.9246|0.76|0.6957|0.64|0.7312|0.60|0.8962|0.90|
|42|175000(1:2.5)|no stop_words|0.9176|0.85|0.9405|0.80|0.6700|0.56|0.7283|0.53|0.8947|0.89|
|42|300000(1:5.0)|no stop_words|0.9390|0.80|0.9470|0.80|0.6234|0.43|0.7098|0.42|0.8735|0.86|

### 4. Test model on the other domains
####  Datasets:
#####    Video Games 5 (174989 pos / 28516 neg)
#####    Digital Music 5 (52116 pos / 5801 neg)
#####    Office Products 5  (45342 pos / 2856 neg)

#### Model params - the same as above; was trained on balanced Movie dataset (185k / 185k)
#### Results:
|Domain|Accuracy(total)|F1-score(negative class)|Precision(negative class)|Recall(negative class)|
:----|:------------|:----|:----|:----:|
|Video Games|0.8798|0.68|0.54|0.90|
|Digital Music|0.9141|0.67|0.54|0.87|
|Office Products|0.8182|0.36|0.23|0.88|
