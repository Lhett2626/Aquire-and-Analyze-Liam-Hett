# Aquire-and-Analyze-Liam-Hett

A description of each file:

Yelp_Reviews:

I got these reviews from the Yelp Fusion API. This was an awesome API when I found out how to access it. In case you are interested in using this api, use this link: https://www.yelp.com/developers/documentation/v3/authentication. 

This information includes restaurant name, yelp url, number of reviews, rating, price, phone number, and address. The files are fairly small. The file with all restaurants is 58 KB and contains 11 columns and contains information on 208 Missoula restaurants. Each restaurant has small file around 600 bites and contains 3 reviews.

Google_Reviews:

I used the Google API, specifically the Google Places and Google Geocoding apis, to pull restaurants reviews in Missoula. I can use the same notebook to find reviews for any area. I came up with the idea when I couldn't decided on a restaurant to go to. I was thinking what do others consider the best restaurant in Missoula. When I looked at google and yelp, I noticed there was a significant difference between the top rated restaurants. Thought it would be cool to compare.

The Google API is great. It has a ton of parameters that I could include. The limitation is that to pull all businesses in an area I only figured out how to search by coordinates and distance from those coordinates. I am able to type in a city/sub region and get the coordinates for that search. However, I can only search by radius around or closest to those coordinates. Towns, Cities and subregions are not perfect circles so finding restaurants in a given town is not perfect.

The other major flaw with the program is that Google API only returns 60 results. I was thinking about making a hackie workaround but after researching it found that it is against Google's terms and conditions. They want to prevent people from using their API to scrape all businesses in an area. I doubt Google would have caught on to me pulling data from different coordinates in Missoula until I got a full list of restaurants but why risk it.

The data set with all restaurants listed is small, only 57 restaurants after cleaning. However, each restaurant has a separate csv file labeled as its name with the last 5 reviews they received on google. 



