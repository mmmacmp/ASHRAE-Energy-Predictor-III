# ASHRAE-Energy-Predictor-III
## Data preprocessing
### Dataset files
* Train.csv
* Test.csv
* Building_meta.csv2
* Weather_train.csv
* Weather_test.csv
### Preprocessing
* The first step is to have train data frame and test data frame so
we merge {train.csv, weather_train.csv, building_meta.csv} as
train_dataframe and we merge {test.csv, weather_test.csv,
building_meta.csv} as test_dataframe.
* Eliminate unuseful features.
* Convert timestamp feature into more descriptive and useful
features {month, day}.
* Fill na values in the data each feature with the appropriate
approach filling.
* Convert categorical features into
indexed_categorical_features.
* Split data into train, test and validation sets.
## Exploratory Data Analysis
### 1
![Alt text](EDA_assets/1.png?raw=true)
Most readings in our dataset measure electricity Which means
when we try to predict electricity meter consumption it should be
better than hot water meter.
### 2
![Alt text](EDA_assets/5.png?raw=true)
Energy consumption by electricity is average over months. There
are no peaks here as electricity consumption doesn't depend
much on the seasons. As we observe Energy consumption by hot
water peaks at winter's months as predicted, While by observing3
Chilled water we find that peaks during summer's months. All of
that says that the month is a good feature.
### 3
![Alt text](EDA_assets/2.png?raw=true)
Generating Steam Consumes most energy. Meter_type is an
important feature.
### 4
![Alt text](EDA_assets/3.png?raw=true)
Reading is much higher during regular work hours, as expected.
So I was thinking that hour might be a descriptive feature but
when fitting without it the model behaves more accurately.
### 5
![Alt text](EDA_assets/4.png?raw=true)
Religious worship locations consume the least amount of energy they are undoubtedly visited less frequently than the others. We
also observe that healthcare, Education, and services consume
much more energy. Which Primary use is an important feature to
predict on it. This has a business value to the government that it
can increase the price according to the type of the building to5
make each type consume energy moderately.
## Proposed solution
### Model
We tried various models but this is the one that gave me best accuracy a regular deep neural network with dense layers using RELU activation and batch normalization layers to give us stable training and using a dropout layer to reduce overfitting.
![Alt text](EDA_assets/6.png?raw=true)
### Results and evaluation
Model Accuracy on train and evaluation data
![Alt text](EDA_assets/7.png?raw=true)
Model Accuracy on test data
![Alt text](EDA_assets/8.png?raw=true)
