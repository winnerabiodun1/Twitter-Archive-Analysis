# WeRateDogs TWitter Api Exploration
## by (Winner Abiodun)


## Wrangle Report

> The dataset that that was wrangled (and analyzed and visualized) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10(most cases with more than 10 denominators involve multiple dogs). The numerators are mostly always greater than 10.This is because they have a unique rating system that permits that.

The project is divided into 3 parts

The wrangle Act- The Notebook where the wrangling and explorations were done.

The Wrangle Report- A direct copy of the readme file that briefly describes your wrangling efforts. To be framed as an internal document.

The Act Report- Serves as a presentation that communicates all the insights and displays the visualizations produced from the wrangled data. 


### “Where the dogs at Brent?” – Data Gathering

> WeRateDogs downloaded their Twitter archive and sent it to Udacity exclusively for this project. This archive contains basic tweet data (tweet ID, timestamp, text, etc.)
All three pieces of data for this project were gathered and loaded in the notebook.
The following libraries were imported- Pandas, numpy, matplotlib, requests, seaborn amongst others
The first dataset was a direct download of the WeRateDogs Twitter archive data (twitter_archive_enhanced.csv) and was read into a pandas dataframe called archive. The second dataset was read to a (image_predictions.csv) file using the requests library, this csv file was read into a pandas dataframe (images) using the read_csv function. The third data set was gotten from the twitter API I applied for, the tweepy library was used since access to the necessary tokens was passed. 
A for loop was used to query the APi’s for the tweet data, the tweets were then dumped to a file(tweet_json.txt) using the json.dumps function of the json library and through the tweet id of the archive dataframe. An exception block was used to catch errors and the error id were appended to a list.
The process took about 40 minutes, a total of 2356 were written into the file successfully while 29 were unsuccessful
Using a for loop and a context handler the tweet_json.txt file was read line by line and the tweet_id, retweet count and favorite count were extracted and appended to an empty list created(extract_list). The list was read into a pandas Dataframe (add_tweet) using the pd.DataFrame function and the columns were specified
The three data frames gathered for the project are archive, images and add_tweet. 

### “Who Let the dogs at out?” – Assessing Data

> The three dataframes were assessed for quality issues and tidiness issues
Eight quality issues and Two tidiness issues were detected through visual and programmatic assessment, carried out simultaneously. Various pandas functions and methods were useful to the assessment some of which includes the info(to show the columns their notnull values and their data types), describe(to describe the dataframe in terms of the count,mean,max,median e.t.c), duplicated(To search for duplicated data), isnull(To check for null values), value_counts(To check the count of each variable in the column of the data frame) e.t.c. among the issues documented are the enormous amount of missing data in the archive table, the href formatting in the source column of the archive table and the erroneous data types. The tidiness rules were violated since the data sets should be combined and the dog stages were divided into 4 different columns.

### “The dogs made a mess!!!” – Data Cleaning

> Here the identified quality and tidiness issues identified during assessment were cleaned. Since we needed original tweet data from the dataset, the not null cells in the retweet column were dropped and then the retweet column was also dopped along with its compatriots. The Source column was also cleaned, Then the data set was combined into one dataframe based on the tweet ids


### “The clean dogs get the fattest bones!” – Data Cleaning

> The combined dataset was stored to a csv file which was later used for further analysis




