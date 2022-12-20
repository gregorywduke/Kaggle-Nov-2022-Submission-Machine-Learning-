# Project Assignments 

* [Project Proposal](https://canvas.txstate.edu/courses/1993336/quizzes/6830611) 
* [Project Progress](https://canvas.txstate.edu/courses/1993336/assignments/27480554) 
* [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566) 


# PROJECT FORMAT

#  KAGGLE NOV2022
**<All Authors>** 

## Project Summary

<Complete for [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566) assignment submission. See github.com repositories on how people shortblurb thre project e.g. REMOVE: It is a standalone section. It is written to give the reader a summary of your work. Be sure to specific, yet brief. Write this paragraph last (150-300 words)

<Fully rewrite the summary as the last step for the [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>


## Problem Statement 

< Complete for [Project Progress](https://canvas.txstate.edu/courses/1993336/assignments/27480554)>

* Give a clear and complete statement of the problem.
    The task for the November 22 TPS is to forecast whether 20,000 samples will have the label "0" or "1," utilizing the available ground truth labels on an additional 20,000 samples to inform our forecasts. This is a binary classification job, but it has a nice twist: instead of being given a dataset from which to build our model, we are given the past predictions of 5,000 classifiers that were built for us. Our submitted forecasts will be a collection of these previously produced forecasts.
* What is the benchmark you are using.  Why?  
    We will use each model's score to benchmark it's performance. We will then calculate the mean squared
    error between our new predictions and the ground truth labels provided as an additional means of benchmarking.
* Where does the data come from, what are its characteristics? Include informal success measures (e.g. accuracy on cross-validated data, without specifying ROC or precision/recall etc) that you planned to use.
    The data was provided by the Kaggle Novemeber 2022 Competition. The data consists of 5000 submission files, a sample submission file, and the ground truth labels for the first half of the submission rows. We plan to classify our predictions for the first submission file by comparing the two, our predictions and the original file's predictions. We will maintain two counter variables and compare the files, which will provide to us an informal
measure of our success. Ideally, we'd want a majority of our predictions to improve upon the original file's predictions. 
* What do you hope to achieve?>
    We want to ensemble submission files in such a way that produces better overall predictions.

<Expand and Complete for [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>

## Dataset 

<Complete for [Project Progress](https://canvas.txstate.edu/courses/1993336/assignments/27480554)>

* Description of the dataset (dimensions, names of variables with their description) If in doubt, use 3.1-3.3. [Datasheets For Datasets](https://arxiv.org/abs/1803.09010) as a guideline.  
    We have a training file with two columns, an index, and labels [0,1] containing 20,000 rows, which will be the truth table. Then we have 5000 files, each with two columns—one for index and one for prediction of the labels- individually containing 40,000 rows, with a combined 200 million data points for predictions. 
* If you are using benchmarks, describe the data in details. If you are collecting data, describe why, how, data format, volume, labeling, etc.>
    Data is the prediction that is the out put of some models that we don't know. We have 5000 files that each of them have predictions for 40000 ID's which are supposed to be between 0-1 and some are not so they will be normalized.

<Expand and complete for [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>

* What Processing Tools have you used.  Why?  Add final images from jupyter notebook. Use questions from 3.4 of the [Datasheets For Datasets](https://arxiv.org/abs/1803.09010) paper for a guide.>  


## Exploratory Data Analysis 

<Complete for [Project Progress](https://canvas.txstate.edu/courses/1993336/assignments/27480554)>

* What EDA graphs you are planning to use? 
    We have primarily been using histograms to explore and analyze our data. Plotting the predictions of a single submission file provides us the prediction range. We also plan to plot the average prediction per ID of each submission file. 
* Why? - Add figures if any
    By averaging the predictions per ID, we can visualize the entire dataset. This will allow us to better understand the scope of the data, and to account for any discreptancies in the range, like predictions that exceed 1.0. 
    https://imgur.com/a/7tDZDj1

<Expand and complete for [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>

* Describe the methods you explored (usually algorithms, or data wrangling approaches). 
  * Include images. 
* Justify methods for feature normalization selection and the modeling approach you are planning to use. 

## Data Preprocessing 

<Complete for [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>


* Have you considered Dimensionality Reduction or Scaling? 
  * If yes, include steps here.  
* What did you consider but *not* use? Why? 

<Expand and complete for [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>


## Machine Learning Approaches

<Complete [Project Progress](https://canvas.txstate.edu/courses/1993336/assignments/27480554)>

* What is your baseline evaluation setup? Why? 
    We plan to use the .score method to evaluate our models. We will also calculate the MSE between our predictions and the original submission's predictions to determine success per row. We will probably take the average of all 5,000 MSE calculations to determine our general success. 
* Describe the ML methods that you consider using and what is the reason for their choice? 
   * What is the family of machine learning algorithms you are using and why?
    We plan to use Random Forest Boosting, Bagging, and Gradient Boosting methods. We are using exclusively ensemble techniques as per the Kaggle Competition description. These techniques fall under the Supervised Learning family, made possible by the data's shape: we already have the ground truth labels. 

<Expand and complete for [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>

* Describe the methods/datasets (you can have unscaled, selected, scaled version, multiple data farmes) that you ended up using for modeling. 

* Justify the selection of machine learning tools you have used
  * How they informed the next steps? 
* Make sure to include at least twp models: (1) baseline model, and (2) improvement model(s).  
   * The baseline model  is typically the simplest model that's applicable to that data problem, something we have learned in the class. 
   * Improvement model(s) are available on Kaggle challenge site, and you can research github.com and papers with code for approaches.  

## Experiments 

<Complete for the [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>

This section should only contain final version of the experiments. Please use visualizations whenever possible.
* Describe how did you evaluate your solution 
  * What evaluation metrics did you use? 
* Describe a baseline model. 
  * How much did your model outperform the baseline?  
* Were there other models evaluated on the same dataset(s)? 
  * How did your model do in comparison to theirs? 
  * Show graphs/tables with results 
  * Present error analysis and suggestions for future improvement. 

## Conclusion
<Complete for the [Project Submission](https://canvas.txstate.edu/courses/1993336/assignments/27480566)>

* What did not work? 
* What do you think why? 
* What were approaches, tuning model parameters you have tried? 
* What features worked well and what didn't? 
* When describing methods that didn't work, make clear how they failed and any evaluation metrics you used to decide so. 
* How was that a data-driven decision? Be consise, all details can be left in .ipynb

 
 **Submission Format** 
 
1. Python code with markdown documentation, images saved in .jpg or .png format, and README.md as a project report
2. Jupyter notebook (.ipynb) that contains full markdown sections as listed above 

## Now go back and write the summary at the top of the page
