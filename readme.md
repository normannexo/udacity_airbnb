# Udacity - Data Scientist Nanodegree
## Project 1: Write a data science blog post

### Exploring Airbnb data for London

Link to the [blog post on Medium](https://medium.com/@normannexo/airbnb-data-london-8e29e3ad8484)

## 1. Introduction/Business Understanding
Despite the ongoing global turmoil caused by the spread of the novel coronavirus and the restrictions
of movement that people have to live with to contain the threat, it's safe to say that the people's desire
to travel to foreign countries and cities will be unbroken in the foreseeable future and travel platforms
like Airbnb will prosper again and keep being attractive for tourists and potential hosts.
But when you consider becoming a host on Airbnb you might want to gain a few insights before you publish your
first offer on the internet. The answers to the following questions might be of particular interest.

1. *What is the price distribution of listings in a specific city?*
2. *Given the room type, the amenities and the location you plan to offer: Which price should you determine for your listing?*
3. *How do you write an attractive description text for your listing?*

## 2. Data understanding
To address our questions we will use data from http://insideairbnb.com/index.html, a website sourcing publicly available information from the Airbnb site. This data includes listings of accomodations of more than hundred cities worldwide, along with geo data of the cities' neighbourhoods. We will use the price, room type and amenities information of the listings to build a meaningful and characteristic feature set for a regression model.

Data used in the project:
Airbnb data from http://insideairbnb.com/index.html:

`listings.csv` - detailed information on the listings of a specific city
`neighbourhoods.csv`
`neighbourhoods.geojson` GeoJSON file of neighbourhoods of the city, used for visualisations.
These data have all we need to be able to address our questions:

We will use information on prices, location and neighbourhoods from the listings file to analyze the price distribution.
We will use price, room type, property type, accommodates and amenities information of the listings file to build a meaningful and characeristic feature set for a regression model.
We will use the description text of the listings file to analyze a few properties of successful description texts.

## 3. Data preparation
The most effort had to be put into the wrangling and cleaning part with the listings file:
- identifying the essential columns for our work and dropped all others
- conversion of price column
- reducing the data set to listings within the 0.95 price quantile
- in our regression model we had to carry out extensive feature engineering with the creation of dummy variables for several columns
- for our text analysis we had to tokenize and apply POS-tag to Description texts.

## 4. Model
We addressed our questions with the following methods 
1. *What is the price distribution of listings in London?*
We applied standard pandas functions and appropriate visualizations to gain insight into the price data and its geographical distribution.

2. *Given the room type, the amenities and the location you plan to offer: Which price should you determine for your listing?*
We built a linear regression model with Ridge regularization and applied appropriate feature engineering and used splitting of test and training data and MSE and visualizations to assess its success. 

3. *How do you write an attractive description text for your listing?*
We concentrated on the key adjectives and nouns used in successful listings and extracted them with the NLTK library.

## 5. Results
1. We learned that the median price in London is about 80.00 $ and gained an impression how the price levels are distributed over the city.
2. We reached a preliminary regression model that is able to predict prices for typical parameters at hand when publishing a new accommodation. But we saw that there still is some headroom for further improvement. For example, by applying more sophisticated feature engineering or by gathering additional data.
3. We identified the most frequent adjectives and nouns used in description texts as one of the aspects of creating attractive descriptions for an accommodation listings.

Also see this blog post.

### Files
- `airbnb.ipynb` - the main jupyter notebook file containg the data analysis


### Used libraries
- pandas
- folium 
- NLTK
- missingno
- wordcloud

### Acknowledgements

The data used in this repository was compiled by http://insideairbnb.com/index.html

