<img width=500 src='https://media1.giphy.com/media/bn86qaAWmQKZ2/giphy.gif?cid=ecf05e47rgml1rrt8s6dlduvpo6dgarx3g12zrjhawzagybi&rid=giphy.gif&ct=g'>

# Analysing Queen's Discography     
> _A sentiment analysis on the song lyrics of  one of the greatest bands of all time_
----

## Goal
This this a NLP project aimed to find insights about how Queen's song lyrics. The goal is to answer the following quesitons: 
<ol>
1. How does the `sentiment level` of an album influences it's popularity? <br> 
2. What is the overal sentiment 'inclination' of the band? Do they tend to `feel more the blues` or be more about the `good times`? _(in other words: what is the distribution of polarization)_ <br>
3. What are the most used words on Queen's lyrics? 
4. What are the most used words across time?
</ol>
<br>


## Libraries:
<ol>
    <li> 1. Libraries: </li>
    <ul> 
        <li>pandas</li>
        <li>re </li>
        <li>sqlalchemy </li>
        <li>getpass </li>
        <li>re </li>
        <li>datetime </li>
        <li>nltk</li>
        <li>sklearn </li>
        <li>lyricsgenius</li>
        <li>dot env</li>
    </ul>
</ol> 


## Data Sources: 
<ol>
    <li>Queen's Discography and songs: Spotify API </li>
    <li>Song lyrics: Genius API </li>
     
</ol>     

<br>


## Process / Methodology

## Part I - Extraction 

### 1. Spotify Token
1. Get Auth for App
- Client_ID
- Client_Secret

2. Get Auth for queries
- token

### 2. Get Queen's (Studio) Albumns

1. url_base: core api url. 

2. [get several albumns query from api](https://developer.spotify.com/console/get-several-albums/)

3. split & join albumns ids for the query

### 3. Filtered dictionary of Albums
1. Find relevant values for analysis (e.g. album_name, release_data, album_cover, etc)
2. Create function to loops through response and return all value in new, filtered, dict_

### 4. Create data frame of filtered_dict 

## Part II - Transformation

### 1. Import csv from extraction notebook

### 2. Tranformation and Enrichment Process:
1. Drop NaNs
2. Replace paranthesis, brackets, line breaks, and tabs
3. Transform the column `release date` to datetime
4. remove stop words and keep unique. 
4. Transform all words to lower case
5. Apply Stem Function to eliminate words suffixes. 
6. Apply Textblob polarity method to calculate lyrics sentiment
7. Assign category to lyrcs based on polarity

### 3. Create DataFrame(s) cleaned-lyrics and words-analysis for loading and enriching

<br>


## Sentiment Analysis
<br>

> click [here](https://public.tableau.com/views/Queen_Sentiment-Analysis-Dashboard_I/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link) and [here](https://public.tableau.com/views/Queen_Sentiment-Analysis-Dashboard_II/Dashboard2?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link) for full visualization of the graphs

### Q.1.: How does the `sentiment level` of an album influences it's popularity? <br>  

<img width=800 src='images\sentiment-level_vs_popularity.png'>

<br>


### Q.2. What is the overal sentiment 'inclination' of the band? Do they tend to `feel more the blues` or be more about the `good times`?

<img width=800 src='images\polarity-distribution.png'>

<img width=800 src='images\count of songs sentiments.png'>

<br>


### Q.3. What are the most used words on Queen's lyrics?

<img width=800 src='images\Most used words.png'>

<br>


### Q.4. What are the top 10 most most popular words across time?

<img width=800 src='images\Use of words across time.png'>




