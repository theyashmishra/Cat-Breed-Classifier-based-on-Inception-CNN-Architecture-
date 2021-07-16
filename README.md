# Cat-Breed-Classifier-based-on-Inception-CNN-Architecture-

The Task is to predict breed of the cat with its picture,using a model which build on *Inception CNN Architecture*.
I have used deep learning libraries keras and tensorflow ,I have build my model with pretrained Inceptionv3 along with some CNN layers on google colab.

## Model building approach
### Importing Libraries
All important libraries are imported which are going to use in the model building keras,tensorflow, scipy visualizatio matplotlib,data preprocessing(imagegenerator, train_test_split), evaluation metrics(accuracy,f1-score).

### Importing Datasets
Datasets is large enough so I used kaggle api to import data directly from kaggle,using api command .
![image](https://user-images.githubusercontent.com/49396916/126012715-61c4f17f-0b21-4ac4-b8c6-b40fb0c9da5c.png)

### Data Preprocessing
Combining all file folder to make a single dataframe of image path and image categories and convert it to a dataframe.
Then filter out rest of categories and kept only specified categories.

### Data Preprocessing
images of dataframe are rotated ,resized ,rescaled, flipped, etc by which our model will be able to deal with all rescaled images of these classes. split data into train ,test, validation, ratio of train to test size is 8 : 10
![image](https://user-images.githubusercontent.com/49396916/126013178-ec3235da-0e2b-4218-9e8e-205521cc0df4.png)

### Model Building 
Model is build using Inceptionv3 model along with cnn layers with input shape (299,299,3).
weight modification was'nt allowed in my model during fitting.

### Model fitting and prediction
Model is fitted on train data with 25 epochs ,batch size=175 and validation size=44, it took about 40 mins for training model with accuracy of 69 % and predict is done on test data(x_test)
![image](https://user-images.githubusercontent.com/49396916/126013903-5bedc442-b578-44c4-9ee6-d0ee6df4de1d.png)

### Evaluation metrics
1:- Accuracy= 66.5%

2:- F1 Score= 65

3:- confusion matrix= [206,   0,   0,  16,   5,   0,   0,   1,  17,   0],
     
     [  3,   7,   0,  18,  25,   0,   0,   6,  22,   0],
     
     [  7,   0,  11,   8,   3,   0,   0,   9,   7,   0],
     
     [  2,   1,   0, 325,  82,   0,   0,   7,   4,   2],
     
     [  0,   1,   0, 154, 270,   0,   0,   7,  19,   2],
     
     [  3,   0,   1,   5,   1,  98,   0,  71,   1,   2],
     
     [  5,   0,   0,   4,   6,   0,   0,   1,   1,   0],
     
     [  4,   1,   4,  32,  36,  34,   0, 249,   9,   5],
     
     [  3,   0,   0,   2,  11,   0,   0,   1, 226,   0],
     
     [  2,   0,   0,   6,  10,   1,   0,   4,   1,   1]

4:- ROC-AUC-Score=90
