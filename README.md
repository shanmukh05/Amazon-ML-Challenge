# Amazon-ML-Challenge

## Team : Elementals
## [Prateek](https://www.linkedin.com/in/prateekagrawal1405/) | [Manish](https://www.linkedin.com/in/manish-sharma-355ba3189/) | [Adhesh](https://www.linkedin.com/in/adhesh-reghu/) | [Shanmukh](https://www.linkedin.com/in/shanmukha-sainath-1045b2197/)

## Details of Files
- `amazon_ml_preprocessing.ipynb` : code to preprocess text
- `amazon_ml_translation_csv.ipynb` : code to translate
non-english text
- `amazon_ml_mode.ipynb` : code to create submission file from
multiple submission files using mode technique
- `amazon_ml_training.ipynb` : code to train embeddings and
predict on test embeddings
- `amazon_ml_embeddings.ipynb` : code to generate embeddings
from csv file
- `submission_top-score.csv` : submission file with top score [Accuracy : `66.85`]

## Details of Competition

- Competition : Multi Class Text Classification
- Host : Hacker-Earth
- Metric : Accuracy
- Time of Competition : 2days:23hrs:59min
- [Checkout competition here](https://www.hackerearth.com/challenges/competitive/amazon-ml-challenge/)

## Details of Data

-  Key column – `PRODUCT_ID`
- Input features – `TITLE`, `DESCRIPTION`, `BULLET_POINTS`, `BRAND`
- Target column – `BROWSE_NODE_ID`
- Train dataset size – `2,903,024`
- Number of classes in Train – `9,919`
- Overall Test dataset size – `110,775`

## Data Preprocessing

### Libraries used:
- `re`
- `langdetect`
- `deep-translator`

### Steps followed:
- Removed special characters and emojis using re.
- Translated non-english text to english using langdetect and
deep-translator.
- Removed stop-words.
- Decontracted some of the words.

## Our Approach
### Libraries used:

- `Sentence_transoformer`
- `RAPIDS`

### Steps followed:

- First the text is converted to embeddings using pre-trained models
such as `paraphrase-mpnet-base-v2` , `paraphrase-MiniLM-L6-v2`
`paraphrase-MiniLM-L3-v2`
- Dimension of Embeddings : `384`
- Embeddings of training data are sent into `KNNClassifier` present in `CuML` library
- Then the trained KNNClassifier is used to predict on test embeddings.
- We also used mode technique i.e. using most frequently predicted label obtained
from different experiments
- `Cross Validation` is also used to train `KNNClassifier`

## Experiments
- Used `NearestNeighbour`, `SVM`, `RandomForest Classifier`
techniques but results are not better compared to KNNClassifier.
- Different size embeddings `(384,768)`
- Combined TITLE,DESCRIPTION and TITLE,DESCRIPTION,
BULLET_POINTS and TITLE, DESCRIPTION, BULLET_POINTS


