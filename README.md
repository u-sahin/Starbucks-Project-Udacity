# Starbucks Capstone Project

### Table of Contents

1. [Installation](#installation)
2. [Project Overview](#overview)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Licensing, Authors, and Acknowledgements](#licensing)


## Installation  <a name="installation"></a>

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the required packages.
There is a `requirements.txt` file which contains all required libraries.
You can install all of them by simply calling it as following:

`pip install -r requirements.txt`


## Project Overview <a name="overview"></a>

In this project, I analyzed data from Starbucks to build a model for improving the choices for the offers.

The json data that is included in this project contains simulated offers that were distributed by Starbucks. 
My goal was to develop a machine learning algorithm that evaluates these offers.

This project could help Starbucks, since they would be able to create new analyzes for themselves which would give them the accuracy of the predictions made by the algorithm.
My personal goal was to build an analysis (something practical) for the Starbucks company in order to help them by making the choices more efficient

## File Descriptions <a name="files"></a>

#### Jupyter-Notebook files
* [Starbucks_Capstone_notebook.ipynb](https://github.com/u-sahin/Starbucks-Project-Udacity/blob/main/Starbucks_Capstone_notebook.ipynb)  
Contains the code

#### Data files
* [profile.json](https://github.com/u-sahin/Starbucks-Project-Udacity/blob/main/data/profile.json)  
Rewards program users (17,000 users x 5 fields)
  * *gender*: (categorical) M, F, O, or null
  * *age*: (int) missing value encoded as 118 
  * *id*: (string/hash)  
  * *became_member_on*: (int) the date as int were the customer became a member
  * *income*: (int) the income of the member
  
* [portfolio.json](https://github.com/u-sahin/Starbucks-Project-Udacity/blob/main/data/portfolio.json)
Offers sent during 30-day test period (10 offers x 6 fields)
  * *reward*: (int) money awarded for the amount spent
  * *channels*: (list) web, email, mobile, social 
  * *difficulty: (int) money required to be spent to receive reward 
  * *duration*: (int) time for offer to be open, in days
  * *offer_type*: (string) bogo, discount, informational
  * *id*: (string/hash)  
  
* [transcript.json](https://github.com/u-sahin/Starbucks-Project-Udacity/blob/main/data/transcript.json)  
Event log (306,648 events x 4 fields)
  * *person*: (string/hash) 
  * *event*: (string) contains the offer type out of [offer received, offer viewed, transaction, offer completed]
  * *value*: (dictionary) different values depending on event type 
    * *offer id*: (string/hash) not associated with any "transaction" 
	* *amount*: (int) money spent in "transaction" 
	* *reward*: (int) money gained from "offer completed"
  * *time*: (int) hours after start of test


* [data.csv](https://github.com/u-sahin/Starbucks-Project-Udacity/blob/main/data/data.csv)  
A temporary csv-file created to ensure a checkpoint in the coding process.


#### Template files
* [Starbucks_Capstone_notebook.html](https://github.com/u-sahin/Starbucks-Project-Udacity/blob/main/Starbucks_Capstone_notebook.html)  
Contains the jupyter notebook in html format

## Results <a name="results"></a>
The main findings of the code and a detailed analysis can be found at the post available [here: medium.com](https://uemitsahin.medium.com/starbucks-capstone-project-f029d2b599f5).

I think it is obvious that this project was very challenging, due to the structure of the data
As shown in the ‘Detection’ in the post, the predictions were wrongly analyzed as ‘offer received’. 
This is due to the amount of occurences of the offer type.
While majority classes were performing well, minority classes didn’t perform well, due to the imbalanced dataset.

After changing the sample amount of each event, I was able to increase the accuracy by a tiny bit.
This shows that, with a more balanced dataset, it is possible to increase the accuracy.

## Licensing, Authors, Acknowledgements, etc. <a name="licensing"></a>
Must give credit to Starbucks for the data.
Otherwise, feel free to use the code here as you would like! 
