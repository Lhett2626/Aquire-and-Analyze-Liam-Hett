# Aquire-and-Analyze-Liam-Hett

This is an assignment for Text-Mining.

Yelp_Reviews:

I got these reviews from the Yelp Fusion API. This was an awesome API when I found out how to access it. In case you are interested in using this api, use this link: https://www.yelp.com/developers/documentation/v3/authentication. 

This information includes restaurant name, yelp url, number of reviews, rating, price, phone number, and address. The files are fairly small. The file with all restaurants is 58 KB and contains 11 columns and contains information on 208 Missoula restaurants. Each restaurant has small file around 600 bites and contains 3 reviews.

Google_Reviews:

I used the Google API, specifically the Google Places and Google Geocoding API, to pull restaurants reviews in Missoula. I can use the same notebook to find reviews for any area. I came up with the idea when I couldn't decided on a restaurant to go to. I was thinking what do others consider the best restaurant in Missoula. When I looked at google and yelp, I noticed there was a significant difference between the top rated restaurants. Thought it would be cool to compare.

The Google API is great. It has a ton of parameters that I could include. The limitation is that to pull all businesses in an area I only figured out how to search by coordinates and distance from those coordinates. I am able to type in a city/sub region and get the coordinates for that search. However, I can only search by radius around or closest to those coordinates. Towns, Cities and subregions are not perfect circles so finding restaurants in a given town is not perfect.

The other major flaw with the program is that Google API only returns 60 results. I was thinking about making a hackie workaround but after researching it found that it is against Google's terms and conditions. They want to prevent people from using their API to scrape all businesses in an area. I doubt Google would have caught on to me pulling data from different coordinates in Missoula until I got a full list of restaurants but why risk it.

The data set with all restaurants listed is small, only 57 restaurants after cleaning. However, each restaurant has a separate csv file labeled as its name with the last 5 reviews they received on google. 


Written Google Reviews and Written Yelp Reviews:

These was a database of reviews used in my analysis. Which restaurant they are associated with is not public. These reviews are being used to train and test a Naive Bayes sentiment prediction model in Analyze notebook.

The Analyze notebook is well documented. The notebook builds the written Google reviews and written Yelp reviews files by iterating through a folder of csv files then combining them in a pandas data frame. I added another column to the data frame called sentiment. This column gives reviews with ratings of 4 and 5 a good sentiment and all other ratings a bad sentiment. This cutoff is completely subjective, but I do not think most restaurants consider a 3-star ratings on Google or Yelp to be good. The sentiment scores are used as y values in the Naive Bayes model. 

I decided to use Yelp reviews as a training set and Google reviews as a test set. Each review was turned into a vector using count vectorizer which can be found in the sklearn package. I could have used another more complex vectorizer but wanted to keep the model simple. A Naive bayes model was fitted to the Yelp reviews. I then used the model to predict Google reviews.

Overall, the model predicted 84% of the reviews correctly. The model did come with a few limitations though. The training set was small for text classification. I only had 530 reviews to train the model. 

After checking some of the misclassified reviews, it makes sense the model wasn't prefect. For example, the below review was 4/5 stars:

'4 Stars because customer service was great. The guy that took my order was friendly, chipper, went out of his way to be nice. The pad thai: Left something to be desired. Not great, tasted like jarred pad thai sauce. Will give another chance because of the great customer service.'

Besides the obvious 4 stars, I would not have assumed this was a good review.

