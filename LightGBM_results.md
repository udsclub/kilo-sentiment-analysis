## LightGBM results for best model (different train size, different test datasets)

### *f1-score was calculated for minor class (negative reviews)
### IMDB and test - same domain as train (Movies), GoodReads - other domain (Books)

|Train sample| Custom Features + TfIdfVectorizer | Model (LGBClassifier) | Valid-acc | Test-acc | Test-acc (IMDB)| Test-acc (GoodReads)| Test-f1 | Test-f1 (IMDB)| Test-f1 (GoodReads)|
|:----------------|:------------|:-------------|:------------|:------------|:------------|:------------|:------------|:------------|:------------:|
|Balanced (50k pos, 50k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000,stop_words=None|reg_lambda=5, n_estimators=200, num_leaves=127, subsample=0.5, colsample_bytree=0.5, subsample_for_bin=10000|0.896|0.895|0.879|0.878|0.71|0.89|0.88|
