| TfidfVectorizer | model_param | val_acc on RT | Test on IMDB | val_acc on IMDB | Test on RT |
|:----------------|:------------|:-------------:|:------------:|:---------------:|:----------:|
|max_df=0.3,min_df=3,ngram_range=(1, 3),max_features=None|n_estimators=50,min_samples_leaf=3|0.766|0.765|0.881|0.702|
|max_df=0.75,ngram_range=(1, 3),max_features=None|n_estimators=50,min_samples_leaf=3|0.767|0.743|0.884|0.694|
|max_df=0.75,min_df=3,ngram_range=(1, 3),max_features=None|n_estimators=50,min_samples_leaf=3|0.762|0.778|0.877|0.703|
|min_df=10, ngram_range=(1, 3),max_features=None|n_estimators=50,min_samples_leaf=3|0.765|0.784|0.874|0.703|
|max_df=0.75, min_df=10, ngram_range=(1, 3),max_features=None,stop_words='english'|n_estimators=50,min_samples_leaf=3|0.755|0.810|0.879|0.709|
|max_df=0.3,min_df=3,ngram_range=(1, 3),max_features=None, stop_words='english'|n_estimators=50,min_samples_leaf=3|0.761|0.813|0.876|0.708|
|max_df=0.75,min_df=3,ngram_range=(1, 3),max_features=None, stop_words='english'|n_estimators=100,min_samples_leaf=3|0.761|0.816|0.886|0.712|

| TfidfVectorizer | model_param | val_acc on RT+IMDB | Test.scv |
|:----------------|:------------|:-------------:|:------------:|
|max_df=0.3,min_df=3,ngram_range=(1, 3),max_features=None|n_estimators=50,min_samples_leaf=3|0.793|0.796|
|max_df=0.75,min_df=3,ngram_range=(1, 2),max_features=25000|n_estimators=100,max_leaf_nodes=2500,min_samples_leaf=3|0.787|0.775|
|max_df=0.3,min_df=3,ngram_range=(1, 3),max_features=None, stop_words='english'|n_estimators=50,min_samples_leaf=3|0.791|0.776|
|max_df=0.75,min_df=3,ngram_range=(1, 3),max_features=None|n_estimators=100,min_samples_leaf=3|0.798|0.798|
