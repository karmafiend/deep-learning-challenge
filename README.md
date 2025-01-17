# deep-learning-challenge
Repo for Data Analytics Module #21 Neural Network Challenge

# Deep Learning Analysis Overview & Report:

# Analysis Purpose: 

Build, train and evaluate a neural network model based on a binary likelihood of gaining project funding. The dataset consists of historical fundraising performance from a leading non-profit fundraising organization, Alphabet Soup in order to build a model that can identify the likelihood of a project successfully gaining funding or not.

# Model Development Process:

This was a multi-step analysis process to build, evaluate and use the neural network model, specifically:

* Data Preprocessing Overview:
  * What variable(s) are the target(s) for your model? For this model, the "Is_Successful" variable capturing in "yes / no" fashion the successful fundraising for a past project served as the "target" variable, defining which organization may be most successful raising funds.
  * What variable(s) are the features for your model? For this model, the "Application_Type" and project "Classification" variables were used since they offered significant amounts of data for use in building and training the model. They also provide some contextual information around fundraising projects making analysis more useful to potential funders (i.e. understanding what types of projects typically see fundraising success).
  * What variable(s) should be removed from the input data because they are neither targets nor features? The remaining variables - "Affiliation," "Use Case," "Organization," "Status," Income Amount," "Special Considerations," and "Ask Amount" - were grouped as "Other" variable category and dropped from the model due to either not enough data being present or for not providing definition for their meaning making use not relevant to funders.

* Compiling, Training, and Evaluating the Model Overview:
  * How many neurons, layers, and activation functions did you select for your neural network model, and why? The original model began with two hidden layers and 8 neurons per hidden layer for a single output. Further updates to these and more are captured in the optimization bullet (#3 in this list) noted below.
  * Were you able to achieve the target model performance? Using TensorFlow with two hidden layers and 8 neurons per lay resulted in a roughly 53-54% accuracy rate, not meeting the 75% goal.
  * What steps did you take in your attempts to increase model performance? Multiple optimization steps were attempted:
    * Optimization 1: Four different tweaks were made to the model itself (not data pre-processing steps) specifically increasing neurons to 16 then 200, implementing the use of Drop Out and Early Stopping techniques to prevent overfitting - these steps did not result in improved accuracy rates. Dropped the use of Drop Out and Early Stopping techniques and instead focused on increasing the original two hidden layers from 2 to 4 and then to 8. This did not result in more accurate results either.
    * ![image](https://github.com/karmafiend/deep-learning-challenge/assets/16076828/096c8112-b69e-428d-88d4-bd6fa1487cb9) Illustrates overall 54% accuracy step after all Optimization #1 changes were tested.
    * Optimization 2: Here multiple optimizer types were tested to determine their effect on improving model accuracy rates. RMSprop Optimizer, SGD Optimizer, and Adagrad optimizer were all tested. These tests did not result in more accurate results.
    * ![image](https://github.com/karmafiend/deep-learning-challenge/assets/16076828/ca6a5d0b-fd4b-49dd-b1dc-bcf356c106b8) Illustrates similar overall accuracy rate of 54% after this stage's round of optimizations.
    * Optimization 3: Moving from model tweaks to those in the data pre-processing stages the most significant (and only) increase in overall accuracy rate came when lowering the minimum counts for both features used: "Classification" (from 3000 to 1000) and "Application Type" (from 1000 to 100). This result improved overall accuracy rate from 54% to 61%. Additional tweaks were made to the models (increased neuron counts, layers, etc.) but did not result in further accuracy improvements.
    * ![image](https://github.com/karmafiend/deep-learning-challenge/assets/16076828/23fcf0f3-1e37-4f71-ab6c-714339af61a7) Illustrates changing "application_type" value count minimum from 3000 to 1000 in the code. Similarly, the minimum count for "classification" was also changed from 1000 to 100 - both of these changes had the biggest improvement of overall accuracy score.
    * ![image](https://github.com/karmafiend/deep-learning-challenge/assets/16076828/40672303-3f99-434f-99c3-10a85c7dbfa4) Illustrates the improved accuracy rate from 54% in optimization 1 & 2 to 61% here.
    * Optimization 4: Using guidance from ChatGPT and XPressAssistant, tested a number of different additional model enhancement techniques (specifically, Polynomial Features, SMOTE and Principal Component Analysis (PCA) were all applied) but still did not result any further accuracy rate improvement.
    * ![image](https://github.com/karmafiend/deep-learning-challenge/assets/16076828/f0f16459-1c17-47ec-8e0c-fd4295b48758) Illustrates that while overall accuracy rate still remained high (namely due to the value count minimum changes in optimization 3) they did not increase further testing these additional techniques. Which is most likely due to the techniques tested here were not necessarily the best for binary models such as the one built here.

Overall, use of the neural network used here via TensorFlow, did not result in a highly accurate model being created. This may be due to there not being enough data in the original dataset but for future analysis I might also consider testing a number of different approaches - Logistic Regression, Support Vector Machines, Naive Bayes, Nearest Neighbor, and Decision Trees for example - to determine if there may be a more suitable model framework that better matches the available data while also providing a more accurate predictive capability. Further testing of these models would help answer the question around the dataset vs. model question this exercise raises.

# Resources used for building supervised machine learning project include:
Primary sources used for this exercise were class instruction and class work along with extensive usage of online how-to content sources, specifically: Google Search, StackOverflow, W3C Schools, and Geeks for Geeks content. ChatGPT and Xpress Assistant used for specific code on Optimization 4 specifically testing the various model enhancement techniques as noted in the optimization code and documentation provided in this repo. 
