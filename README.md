# deep-learning-challenge

## Analysis

The purpose of this analysis is to train a neural network model to help with classification of funding applicants. The data include over 34,000 organization and associated metadata. The goal is to be able to predict whether or not an organization will used the funding to become successful. Two models were trained. The second was an attempt to optimize from the first. Data was preprocessed and then split for training. TensorFlow and keras was used for the neural network model. Number of neurons in the input layer was chosen to be equal to number of features. Number of neurons in the hidden layer was chosen to be near 2/3 of the input. Both compiled with loss="binary_crossentropy" and optimizer="adam".

## Results

* Data Preprocessing
  * Target variable used: IS_SUCCESSFUL
  * Feature variables: APPLICATION TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
  * Variable removed: EIN, NAME
  * Binning:
     * APPLICATION TYPE value count < 200 = 'Other'
     * CLASSIFICATION value count < 1000 = 'Other'
  * Use get_dummies to convert categorical data to numerical     
  * Use StandardScaler   
  * ![image](https://github.com/lhmag89/deep-learning-challenge/assets/119267098/85ff542c-48f2-4a1f-aec7-e85bb37b7b7f)

* Model 1
  * ![image](https://github.com/lhmag89/deep-learning-challenge/assets/119267098/7eb7f616-4a22-4cac-afb5-fc92478a925a)
  * ![image](https://github.com/lhmag89/deep-learning-challenge/assets/119267098/a49856bd-a69f-42d1-a5b2-1a59cb9384d4)
  * Training on 100 epochs. Accuracy: 72.70%
  * Model save to AlphabetSoupCharity.h5 file

* Model 2
  * Modifications:
    * Removed STATUS column
    * APPLICATION TYPE value count < 5 = 'Other'
    * CLASSIFICATION value count < 10 = 'Other'
    * Added 4 additional hidden layers
    * Increased number of neurons
  * ![image](https://github.com/lhmag89/deep-learning-challenge/assets/119267098/a66ee016-6db3-45f2-bbc9-28689fa644cf)
  * ![image](https://github.com/lhmag89/deep-learning-challenge/assets/119267098/d637551f-19ea-4be1-9aa5-847e996e532d)
  * Training on 100 epochs. Accuracy: 73.17%
  * The target accuracy rate of 75% was not achieved

## Summary

The initial model had an accuracy of 72.70% after training. The optimized model showed a modest increase to 73.17%. Neither model achieved the target rate of 75%. Further analysis of these results is needed to be able to recommend a model. Identifying outliers in the dataset would be helpful in trying to improve the model. 

## Technologies
Python, Jupyter, Pandas, tensorflow, sklearn, train_test_split, Keras, StandardScaler

## Contributors
Developed by Luis Hernandez Email: lhernandez.mag.89@gmail.com

## License
UC Berkeley Extension Data Analytics Program
