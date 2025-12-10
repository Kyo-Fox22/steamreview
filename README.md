# Apex Legends Steam Review Analysis

Apex Legends was one of the games I liked to play when I was in high school, but recently it has received really heavy negative ratings in steam, some of which are already present when I was playing such as server issues and network connectivity, but alot of it are new such as the upsurge of hackers within lobbies and the largescale increase of microtransactions that are now in the game. This project generally aims to dive deeper into the reveiews of the game to hopefully gather insights as to what the game's main issues are, key features that keeps players playing, and derive a recommended course of action based on findings.

To do so, the project will consist of three major parts:
1. Scraping the Reviews
2. Processing of Data
3. Analysis and Interpretation of Data

# Scraping the Reviews
In order to get data for analysis, a webscraper will be built in python using the selenium library. This file will then be ran to collect various information from the steam review page of Apex Legends, namely: 
- Author of Review
- Review Content
- # of comments
- Products on Account
- Hours on Account
- Remark
- # of users found review funny
- # of users found review helpful
- Community Awards

These data will be the cornerstone of which the analysis will be made, discovering patterns and major topics that a lot of users frequently talk about in the reviews. The features will also act as a filter to group the reviews into separate parts to further enrich analysis. This separation can narrow down topics for that specific group (i.e.: frequently talked topics for people that recommend the game, have a lot of products on account, lots of hours on the game, or any combination of these)

# Processing the Data
After gathering the data, it will now be thoroughly cleaned. This consist of renaming or adding columns, modifying cell values, correcting data types for analysis, and other similar functions that will make analysis plausible.

# Analysis and Interpretation of Data
The data will be ran through 3 specific methods to identify core topics and issues that frequently occur in the reviews:
1. Wordcloud Generation - to identify frequently discussed topics in all reviews
2. KMeans Clustering - group and classify reviews based on content
3. Topic Extraction - extract keywords or topics per review

4. 
