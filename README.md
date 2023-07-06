# Sentiment-Analysis-of-AirBnb-London

Data Collection:
Data acquisition is the process for bringing data that has been created by a source outside the organization, into the organization, for production use (Malcolm Chisholm, 2018). In simple words it is the process of obtaining, filtering, and cleaning data before it is stored in a data warehouse or another storage method. In many circumstances, data is not in a format that can be easily downloaded and analyzed.
The London Airbnb dataset for this study was obtained from the Inside Airbnb website “Inside Airbnb: Get the Data”, which allows researchers to access publicly available Airbnb data for research purposes, as well as data from numerous previously published Airbnb-related studies. This website stores the data of AirBnb worldwide and to perform the analytics on London City AirBnb, London city was filtered and downloaded the dataset till 09 March 2023. The link to this website is Inside AirBnb: Get the Data.
Data Description:
There are two different datasets; 1. listing.csv and 2. Reviews.csv that are going to be used in this project. Firstly, some basic explorations are done using these both datasets individually. To perform sentiment analysis on reviews, both datasets are combined with performing different data cleaning processes. The essential libraries are installed at the very beginning and other libraries are imported gradually as per the requirements. 
 
Figure 1: Importing essential libraries.

 
Figure 2: Loading listing dataset and visualizing in table form part -1
 
Figure 3: Loading listing dataset and visualizing in table form part -2
 
Figure 4: Loading reviews dataset and visualizing in the table form.
Data Cleaning: 
Cleaning data helps to achieve accuracy in this analysis and improve the performance of the model. The results and findings depend on the data used, thus that data needs to be cleaned properly to get the proper outcome. Here, some of the data cleaning techniques are performed:
1.	Dealing with missing data
To deal with missing values, isnull function is used.
 
Figure 5: Identifying the missing values.
From the figure 5, we can see that some of the columns have missing values including name, neighbourhood group, last review, reviews per month, and license with different numbers. Thus, firstly we will analyse which columns are needed for our analysis. We don’t need columns like last review, name, host name, neighbourhood group, and license. So, we will drop those columns in later stage and for now, the number of reviews column is cleaned as this column is required for our analysis. 

 
Figure 6: Replacing missing data with 0.
As per mentioned above, the missing data in umber of reviews column are replaced by 0. 

2.	Removing unwanted data
As mentioned above, the columns last review, name, host name, neighbourhood group, and license aren’t required for further analysis, so these columns are dropped from our dataframe. 
 
Figure 7: Dropping unwanted columns.

Data-Exploratory Analysis
The practise of identifying patterns, exploring relationships, and extracting information from unfamiliar datasets is known as exploratory data analysis (EDA). Because data scientists generally start with limited knowledge of the data and its structure, the process is iterative. To align the data with the aims of the analysis, data scientists execute a variety of data preparation activities such as identifying outliers, standardising value ranges, and deleting or filling null attributes during an EDA.
Data is used by businesses to solve problems, make intelligent choices, and prepare efficiently for the future. This data is optimised and ready to utilise due to data analysis. The following are some examples of data analysis:
•	Descriptive analysis
•	Diagnostic analysis
•	Predictive analysis
•	Prescriptive analysis
Descriptive Analytics
Descriptive analytics is the interpretation of historical data to better understand changes that have occurred in a business. Descriptive analytics describes the use of a range of historic data to draw comparisons (Jake Frankenfield, 2020). The most often reported financial data, such as year-over-year pricing adjustments, month-over-month sales growth, the number of users, or total revenue per subscriber, are all descriptive analytics products. These metrics all indicate what happened in a company over a specific time. This analytics makes use of a wide range of data to provide an accurate picture of what has transpired in a company and how it compares to previous times. These performance measures can be used to identify areas of strength and weakness, allowing management initiatives to be better informed.
Diagnostic Analytics
Diagnostic analytics describes the techniques you will use to ask your data: Why did this happen? It's a deep dive into your data in quest of useful information. The first step in most firms' data analysis is descriptive analytics, which is a simpler procedure that records the facts of what has already occurred. Diagnostic analytics goes a step further by elucidating the logic behind specific outcomes. Data discovery, drill-down, data mining, and correlations are common strategies used in diagnostic analytics. Analysts pick data sources that will aid them in interpreting the outcomes during the discovery process. Drilling down requires concentrating on a certain aspect of the data or a specific widget. Data mining is an automated method of extracting information from large amounts of raw data. Finding consistent correlations in your data can also assist you in determining the scope of the investigation. 
Predictive Analytics
Predictive analytics is a type of advanced analytics that forecasts activity, behaviour, and trends using current and previous data. It entails using statistical analytic techniques, data searches, and machine learning algorithms to develop predictive models that provide a numerical value to the likelihood of a
specific action or event occurring (Linda Tucci, 2022). The application of statistics and modelling tools to create predictions about future outcomes and performance. This enables businesses and investors to shift their resource allocation to take advantage of potential future developments. Predictive analytics can also be utilised to boost operational efficiency and lower risk.
Prescriptive analytics
Prescriptive analytics has been called “the future of data analytics,” and for good reason. This form of analysis goes beyond explanations and forecasts to suggest the best course of action for the future. It's very handy for making data-driven decisions (Catherine Cote, 2021). Prescriptive analytics frequently employs machine-learning algorithms to sort through enormous amounts of data faster and more efficiently than people. Algorithms search through data and provide recommendations based on a certain set of requirements using "if" and "else" statements. For example, if at least 50% of customers in a dataset said they were "extremely dissatisfied" with your customer support team, the algorithm might suggest more training.

Summary Statistics: 
Summary Statistics helps to identify the mean, median, standard deviation, count, minimum, maximum and quartile information of every columns that have numeric values. 
 
Figure 8: Statistics information of variables

 
Figure 9: Stats of key variables
From the Figure 10, we can see that there are 75241 number of Airbnb properties with 4 room types in 33 different locations inside London where the average review is 17.97%. On average, each property in London has received approximately 17.97% reviews.


 
Figure 10: Number of hosts
There are in total 47619 number of individual hosts where the total number of Airbnb listing is 75241. Some of the hosts have multiple Airbnb hosting. 
Let’s see the available room types:
 
 
There are 4 types of rooms are sold in Airbnb London where the Entire Home/Apartment has 45714 number, Private Rooms are 28910, Shared Rooms are 403 and Hotel Rooms are 214 in number. We can see that mostly the Entire Home and Apartment are famous for Airbnb followed by the Private Rooms.
Which place in London provide more AirBnb facility?
 
Till 09 March 2023, Westminster is the busiest Airbnb area inside the London followed by Tower Hamlets and Hackney whereas the Sutton and havering are the less crowed places for Airbnb. 
 

Which location has the highest availability? 
 
Though there are many AirBnb properties inside the London, some of them are available frequently and some of them mostly. Based on the availability, Bexley and Havering are best options to stay and Hackney and Islington less available. 
Which area are mostly expensive?
 
Westminster, and Kensington are bit expensive as compared to other areas and Sutton, Croydon and Hillington have less room price as compared to other areas.  
Which month has the highest reviews? 
 
Based on the bar graph, November and July are gathering more reviews whereas April and March have less reviews. 

As our target is to analyse the sentiment of users based on the comments, thus, let’s separate only the required columns for our further analysis. 
 
In our case, only the id, host id, location, room type and price are needed from this dataset. So, we created new dataframe and pulled only the required columns. 
Working on Next Dataset; reviews.csv
The reviews dataset contains the information related to the comments given by the Airbnb users in a particular date. 
 
This dataset has in total 7 columns and now, we will perform some basic cleaning operations. 
 
We identified the missing values and separated only the required columns that is listing id and comments. 
Now, let’s merge the two datasets and store the required data in a new dataframe. 
 
For our further analysis, we only need id, comments, host id, location name, room type and price. 
As the dataset was very big, we only used around 10000 data by dropping other data.
 
 
Now, let’s load the positive and negative text file.
 
This helps to classify comments into positive, negative, or neutral sentiment categories based on the presence of words from the positive and negative lists. By counting the occurrences of positive and negative words in each comment, it determines the overall sentiment of the comment. This sentiment analysis approach assumes that the presence of more positive words suggests a positive sentiment, while the presence of more negative words suggests a negative sentiment.

 
The above figure defines a function called comment analyser that takes a list of sentences as input. This function tokenizes each sentence, converts the tokens to lowercase, removes non-alphanumeric tokens, and filters out stop words. It then applies the positive negative checker function to determine whether each sentence is positive, neutral, or negative based on predefined positive and negative word lists. The function counts the number of positive, neutral, and negative comments and returns the results.

The code inserts three new columns, 'positive comment', 'neutral comment', and 'negative comment', into the cleaned df Dataframe. It iterates over each row in the Dataframe, calls the comment analyser function on the comment text in that row, and assigns the counts of positive, neutral, and negative comments to the corresponding columns in the Dataframe.

Overall, this code performs sentiment analysis by analyzing the sentiment of each comment and counting the occurrences of positive, neutral, and negative comments. It provides valuable insights into the sentiment distribution within the dataset. 
 
Now, the positive, negative, and neutral comments are added into the cleaned dataframe along with the required columns. 
Let’s clean and preprocess the comments.
This step prepares the text data for further analysis or modelling tasks where the removal of URLs, HTML tags, numbers, and punctuation marks is desired. The resulting cleaned comments are printed for inspection or subsequent processing.

 
The above figure demonstrates the preprocessing of text data in a Dataframe column named comments. The preprocessing steps involve several functions to clean the text.
First, the column is converted to a string data type for consistency. Then, various transformations are applied using lambda functions. These transformations include removing numbers, URLs, and HTML tags from each comment using regular expressions and predefined functions. Additionally, the comments are converted to lowercase to ensure uniformity in the text data. Punctuation marks are also removed from the comments.
The next step is to perform several text processing and analysis steps. Firstly, the required libraries along with NLTK for natural language processing are installed. The comments column from the cleaned Data Frame is tokenized using the word tokenize function, which breaks down the sentences into individual words and stores them in Token list.
To prepare the tokens for further analysis, punctuation and non-alphanumeric tokens are removed from each tokenized review using a loop that iterates over the indices of Token list. This step helps to clean the data and remove unnecessary characters.
Stop words, which are common words like pronouns and prepositions, are then removed from the tokens using the stop words module from NLTK. The code initializes a set of English stop words and checks each word in Token list to exclude any stop words from the list.
After the preprocessing steps, the code demonstrates the creation of bigrams and trigrams from the modified tokens of the first review. It uses the words to n-grams function to concatenate adjacent words with a separator, generating n-grams for further analysis.
Lastly, the code calculates the frequency distribution of distinct words in the tokens. It utilizes the Freq Dist class from NLTK, initializes an instance of FreqDist, and iterates over each review's tokens to update the frequency count for each word. This frequency distribution provides insights into the occurrence of words in the dataset and can be utilized for various text analysis tasks.
Overall, the above diagram showcases essential steps in text preprocessing, including tokenization, removing punctuation and non-alphanumeric tokens, eliminating stop words, and generating n-grams and frequency distributions. These steps lay the groundwork for further analysis and exploration of the text data.
 
In the above you can see that there are 414140 positive, 13803 neutral and 47637 negative comments words which shows that the number of positive comments is way higher that the negative ones.
Tokenization 
Tokenization is the process of breaking down a large text into smaller tokens. It can be done at the sentence or word level (sentence tokenization) (word tokenization). Cleansing the text: We need to eliminate the special characters and digits from the text in this phase. Python's regular expression operations package can be used.
 
 
 
 
 

What are the most used words?
 
The diagram shows a bar plot showing the frequency distribution of the top 5 most common words in the tokenized reviews.
 
The above code screenshot shows the generation of a word cloud visualization based on the frequency distribution of words in the tokenized reviews. The word cloud represents the most common words, with the size of each word indicating its frequency of occurrence. Stop words are excluded from the word cloud to focus on meaningful words.
 
We can see how word clouds can help users quickly identify the most common tokens in each feature. We can discover frequent terms that appear repeatedly by dividing each string down into individual components. "clean" "great" and comparable qualifiers are, unsurprisingly, the most used across categories. Finally, the comments of the listings review on Airbnb. If we're deciding where to stay based on budget, we might want to check out the neighbourhood reviews. We use the review dataset to see how many good and bad comments there are about the areas. To begin, we look for reviews in English to examine. We then used the NLTK package to do sentiment analysis to determine whether a comment is good or negative.
Classification of Positive, Negative and Neutral Reviews
Now, let’s analyse the positive, negative, and neutral reviews gained by the different locations inside London so that the visitors can get clear insights of the Location they are preferring to make their stay. This analysis will help them to go deep dive into the locations that have positive, negative, or neutral comments. 
Location with the Positive Comments: 

 
From the Figure, we can see that Hillingdon and Richmond upon Thames has the highest positive comments so far. So, the visitors now can make their decision in which locations they can secure and enjoy their stay.
Location with the Negative Comments: 

 
From the above diagram, City of London and Southwark has the highest negative reviews. 

Conclusion 
We identified sources of pleasure and unhappiness among Airbnb consumers in our research. Airbnb customer review studies showing the positive and negative ratings, this study employed equal numbers of positive and negative reviews. Using Python to analyse Airbnb listings and reviews data to build informative charts. When planning a trip to London, one can choose a neighbourhood by looking at average costs, remarks, availability. Following that, we looked at borough and neighbourhood listing densities to see which locations were more popular than others. The more central areas of London we look for Airbnb, the more expensive are the listings. 
As we know that the neighbourhood group column has no values if there has been data it would have been much easier to develop a good visualization as taking whole neighbourhood column for visualization was hard because there were 30+ area listed which made difficulty in plotting the graph. According to the findings Airbnb in London is doing well we can see that as huge number of positive review additional attributes. It would also be useful to have a few of extra characteristics for our data exploration purposes, such as positive and negative numeric 0-5 stars reviews for each listing; having this information would aid in determining the best-reviewed hosts. Overall, we uncovered many intriguing feature connections and detailed each stage of the approach. This data helps organization make better business choices, platform control, marketing activities, new product implementation, and much more.
