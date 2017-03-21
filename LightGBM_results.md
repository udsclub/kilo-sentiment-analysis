## LightGBM results for best model (different train size, different test datasets)

### * f1-score was calculated for minor class (negative reviews)
### * IMDB dataset(25000x2) - same domain as train (Movies), GoodReads dataset (3588x2) - other domain (Books)

|Train sample| Custom Features + TfIdfVectorizer | Model (LGBClassifier) | Valid-acc | Test-acc | Test-acc (IMDB)| Test-acc (GoodReads)| Test-f1 | Test-f1 (IMDB)| Test-f1 (GoodReads)|
|:----------------|:------------|:-------------|:------------|:------------|:------------|:------------|:------------|:------------|:------------:|
|Balanced (50k pos, 50k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000, stop_words=None|rcolsample_bytree=0.7, learning_rate=0.1, max_depth=-1, min_child_samples=15, n_estimators=200, num_leaves=127, reg_lambda=1, scale_pos_weight=1, subsample_for_bin=5000|0.905|0.904|0.887|0.884|0.72|0.89|0.88|
|Balanced (100k pos, 100k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000, stop_words=None|rcolsample_bytree=0.7, learning_rate=0.1, max_depth=-1, min_child_samples=15, n_estimators=200, num_leaves=127, reg_lambda=1, scale_pos_weight=1, subsample_for_bin=5000|0.908|0.910|0.895|0.895|0.74|0.90|0.90|
|Balanced (185k pos, 185k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000, stop_words=None|rcolsample_bytree=0.7, learning_rate=0.1, max_depth=-1, min_child_samples=15, n_estimators=200, num_leaves=127, reg_lambda=1, scale_pos_weight=1, subsample_for_bin=5000|0.909|0.913|0.897|0.896|0.74|0.90|0.89|
|Imbalanced (2:1, 370k pos, 185k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000, stop_words=None|rcolsample_bytree=0.7, learning_rate=0.1, max_depth=-1, min_child_samples=15, n_estimators=200, num_leaves=127, reg_lambda=1, scale_pos_weight=1, subsample_for_bin=5000, **scale_pos_weight=0.5**||||||||
|Imbalanced (2:1, 557k pos, 185k neg)|max_df=0.75, min_df=3,ngram_range=(1, 3), max_features=35000, stop_words=None|rcolsample_bytree=0.7, learning_rate=0.1, max_depth=-1, min_child_samples=15, n_estimators=200, num_leaves=127, reg_lambda=1, scale_pos_weight=1, subsample_for_bin=5000, **scale_pos_weight=0.33**||||||||
