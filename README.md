# Data-Wrangling
Wrangling a dataset about Twitter WeRateDogs

## Overview

Real-world data rarely comes clean. Thus, in the project, the dataset is gathered from a variety of sources and in a variety of formats. After that, the dataset has to be assessed in terms of its quality and tidiness before being cleaned to be a dataset at a good quality. This process is called data wrangling. This report requires all data wrangling steps: gather, assess, and clean, before storing into a complete data file.

This project wrangle, analyse and visualise a dataset about the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators are always greater than 10, because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage. 

## Libraries

- pandas
- NumPy
- requests
- tweepy
- json

## Main steps

- Gathering
- Assessing
- Cleaning

## Data

- Enhanced Twitter Archive

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced." 

- Additional Data via the Twitter API

Back to the basic-ness of Twitter archives: retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. 

- Image Predictions File

A table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images) on URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv.

## Detailed
1. Gathering data
The data for this project is gathered from 3 different sources: from a csv file on hand, a url link and from Twitter API.
The first data file is the WeRateDogs Twitter archive. This file is given on hand. Thus, I just need to download this file manually by clicking in given link.
The second data file is the tweet image predictions, i.e., what breed of dog (or other object, animal, etc.) is present in each tweet according to a neural network. This is a flat file tsv which is hosted on Udacity's servers. I have to download it programmatically using the Requests library of Python. This step requires the author to be familiar with Requests library to download a file programmatically with a given url.
The last dataset contains each tweet's retweet count and favorite ("like") count. In order to acquire this dataset, I had to use the tweet IDs in the file WeRateDogs Twitter archive (the file csv which was downloaded before) to query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file. Each tweet's JSON data should be written to its own line. This step requires the ability to use Tweepy library to query Twitter API.

2. Assessing data
After gathering each of the above pieces of data, I have assessed them visually and programmatically for quality and tidiness issues. This step ensures that the data conforms with the requirements about quality and tidiness.
Quality issues pertain to the content of data. The condition of quality includes completeness, validity (conforming to a defined schema), accuracy and consistency.
Tidiness issues pertain to the structure of data. These structural problems generally prevent easy analysis. Untidy data is also known as messy data. The requirements for tidy data are:
    Each column denotes a variable.
    Each observation is a row.
    Each type of observational unit forms a table.

3. Cleaning Data for this Project
After assessing the issues in quality and tidiness, I clean each of the issues. It includes 3 sub-steps: defining, coding and testing. 

4. Storing
I stored the clean DataFrame(s) in a csv file with the main one named twitter_archive_master.csv.


