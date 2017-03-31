## Base parameters
### Train dataset: Movie and TV_5. Balanced data. Train sample: 200000.
### TfidfVectorizer:
#### max_df=0.75, min_df=3, ngram_range=(1, 3), max_features=None, stop_words='english'
### ExtraTreesClassifier parameters:
#### n_estimators=50,max_leaf_nodes=None,min_samples_leaf=3

|         |precision|recall|f1-score|support|
|:-------:|:-------:|:-------:|:-------:|:-------:|
|     0   |   0.84  |   0.87  |   0.86  |  10000  |
|     1   |   0.87  |   0.84  |   0.85  |  10000  |
|avg/total|   0.86  |  0.85   |   0.85  |  20000  |


#### test predict Digital Music
#### accuracy: 0.8287

|         |precision|recall|f1-score|support|
|:-------:|:-------:|:-------:|:-------:|:-------:|
|     0   |   0.35  |  0.82  |   0.49  |  5801    |
|     1   |   0.98  |  0.83  |   0.90  |  52116   |
|avg/total|   0.91  |  0.83  |   0.86  |  57917   |

#### test predict Video Games
#### accuracy: 0.7309

|         |precision|recall|f1-score|support|
|:-------:|:-------:|:-------:|:-------:|:-------:|
|     0   |   0.33  |  0.87  |   0.47  |  28516    |
|     1   |   0.97  |  0.71  |   0.82  |  174989   |
|avg/total|   0.88  |  0.73  |   0.77  |  203505   |


#### test predict Office Products
#### accuracy: 0.6754

|         |precision|recall|f1-score|support|
|:-------:|:-------:|:-------:|:-------:|:-------:|
|     0   |   0.13  |  0.83  |   0.23  |  2856    |
|     1   |   0.98  |  0.67  |   0.79  |  45342   |
|avg/total|   0.93  |  0.68  |   0.76  |  48198   |
