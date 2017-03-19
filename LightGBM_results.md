## LightGBM results for best model (different train size, different test datasets)

### *f1-score was calculated for minor class (negative reviews)
### * IMDB dataset(25000x2) - same domain as train (Movies), GoodReads dataset (3588x2) - other domain (Books)

|Train sample| Custom Features + TfIdfVectorizer | Model (LGBClassifier) | Valid-acc | Test-acc | Test-acc (IMDB)| Test-acc (GoodReads)| Test-f1 | Test-f1 (IMDB)| Test-f1 (GoodReads)|
|:----------------|:------------|:-------------|:------------|:------------|:------------|:------------|:------------|:------------|:------------:|
|Balanced (50k pos, 50k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000,stop_words=None|reg_lambda=5, n_estimators=200, num_leaves=127, subsample=0.5, colsample_bytree=0.5, subsample_for_bin=10000|0.896|0.895|0.879|0.878|0.71|0.89|0.88|
|Balanced (100k pos, 100k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000,stop_words=None|reg_lambda=5, n_estimators=200, num_leaves=127, subsample=0.5, colsample_bytree=0.5, subsample_for_bin=10000|0.902|0.905|0.889|0.890|0.73|0.89|0.89|
|Balanced (181k pos, 181k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000,stop_words=None|reg_lambda=5, n_estimators=200, num_leaves=127, subsample=0.5, colsample_bytree=0.5, subsample_for_bin=10000|0.907|0.909|0.894|0.894|0.74|0.90|0.89|
