# 550_assignment1
dsci550_assignment1 

This is the first assignment from the DSCI 550 class. This assignment is collaborated and completed by Team 3. <br>
Team menbers: Jimin Ding, Mingyu Zong, Hui Qi, Xiaoyu Dong


# Dependencies

> A list of all of the dependencies used, included their version number  
```
editdistance==0.5.3
elasticsearch==8.6.2
Flask==1.1.2
jellyfish==0.9.0
nltk==3.4.5
numpy==1.21.5
pandas==1.4.4
Pillow==9.4.0
pytesseract==0.3.10
python_Levenshtein==0.20.9
requests==2.23.0
scikit_learn==1.2.1
scipy==1.7.3
simplejson==3.18.3
SolrClient==0.3.1
stemming==1.0.1
tika==1.23.1

```
# Installation

Install the requirements necessary to run your project:  

```
pip install -r requirements.txt
```

# Running the project

```
add_film.py
sarcasm_token.py
add_hatespeech.py
add_sarcasm.py

```

```
3 MIME type.ipynb
```

In the Q2_image_code folder, open Q2_time.ipynb will show the code to visualize feature of users' post time of a day.
```
Q2_time.ipynb
```
In the Q3_image_code folder, open Q3_genders_ages_interests.ipynb will show the code to visualize features among users' interests, genders, and ages.
```
Q3_genders_ages_interests.ipynb
```
In the Q6_Language_Indentification folder, open Q6_Language_Indentification.ipynb will show the code to visualize users' distribution from narratives' language identification.
```
Q6_Language_Indentification.ipynb
```

# Methodology

#### Q5: Add and expand the dataset with sporting events, film festivals, flag for hate speech, and lag for sarcasm

We have the film and sports events period from film_date.txt and sport_date.txt. If a user makes a post (Account Created Date) during these periods, our columns "Film" and "Sport" will enter the name of those events from film_name.txt and sport_name.txt. 
 
We have a list of words in hatespeech.txt to help detect hate speech in our posts. If the title and narrative of the post have more than two marked words in the hatespeech.txt, this post will be flagged as hate speech and shown as "TRUE" in the "ifHate" column in our dataset. The list of words is from the ADL Hate Symbol Database.  


``` 
Levenshtein.ratio
``` 

#### Q6: Identify at least three other datasets, each of different top level MIME type

Our three other datasets have following MIME types:
- image/png
> We find and download three images of positive words (pos1.png, pos2.png, pos3.png). <br>
We import Tesseract to extract text from images and compare them with narratives. We store "TRUE" or "FALSE" depending on whether posts have positive words in these three images in columns Postive Words 1, Postive Words 2, and Postive Words 3.

- application/api+json
> We use a public holiday API to find whether the date of the post is a holiday in each continent or not. We use the request library to parse API responses. (EU_holiday is shortened for Europe; AM_holiday is shortened for Americas; AS_holiday  is shortened for Asia; AF_holiday  is shortened for Africa; OC_holiday is shortened for Oceania holiday names). <br>
If the post date is a holiday, we will input the name of that holiday into its correct position in one of the following columns: Europe Holiday, Americas Holiday, Asia Holiday, Africa Holiday, and Oceania Holiday. And also, enter "TRUE" into Public Holiday Or Not. We will enter "False" into Public Holiday Or Not if it is not a holiday.

- application/zip
> We extract the zip file (owid-covid-data.zip), unzip it, and get csv file for the covid condition. It represents users' interest in health and politics. Cov_cases, cov_deaths, cov_tests, and cov_vaccinations stand for the number of cases, deaths, tests, and vaccinations in a day globally.

#### Q7: Tika-Similarity




