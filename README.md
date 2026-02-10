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
- \# of comments
- Products on Account
- Hours on Account
- Remark
- \# of users found review funny
- \# of users found review helpful
- Community Awards

These data will be the cornerstone of which the analysis will be made, discovering patterns and major topics that a lot of users frequently talk about in the reviews. The features will also act as a filter to group the reviews into separate parts to further enrich analysis. This separation can narrow down topics for that specific group (i.e.: frequently talked topics for people that recommend the game, have a lot of products on account, lots of hours on the game, or any combination of these)

# Processing the Data
After gathering the data, it will now be thoroughly cleaned. This consist of renaming or adding columns, modifying cell values, correcting data types for analysis, and other similar functions that will make analysis plausible.

# Analysis and Interpretation of Data
The data will be ran through 3 specific methods to identify core topics and issues that frequently occur in the reviews:
1. Wordcloud Generation - to identify frequently discussed topics in all reviews
2. KMeans Clustering - group and classify reviews based on content
3. LDA Topic Extraction - extract keywords or topics per review

# Findings
### Wordcloud
The wordcloud doesn't have much to cover due to the repetitive nature of the words inside the reviews. Majority of them have filler words and nonsensical words that are thrown about only for the fun of the community; however, it is still quite beneficial for us to analyze the words according to their frequency within the user reviews.

Looking at the general overview of negative reviews, we can see that users often complain about microtransactions, matchmaking, and servers respectively. Implying that majority of the user find microtransactions an issue, possibly through its high price, followed by the issues within matchmaking and then servers, which may be connected to the reason why users are complaining about microtransactions (devs might be focusing on microtransactions more on fixing issues in matchmaking and servers). Even after segregating the high hour negative reviews and negative reviews that were marked as helpful, these words still come up within the wordcloud, thus highlighting its significance in player dissatisfaction.
### Kmeans
From the Kmeans model, we can see that majority of the negative reviews are classified as either server issues or bad matchmaking. This means that a lot of the playerbase have complained about getting a bad experience with the servers, possibly high ping, lag, or the constant downtime of the servers; in addition, a large percentage have also raised an issue with matchmaking, stating that alot of the players they get matched with belong to a much higher rank than they are, causing unfair play and skill imbalance within the lobby, with the higher ranked players dominating the low ranked.

In contrast, we see that in the positive reviews, majority of the classified content were about the removal of the origin launcher, which seem to have posed a massive issue to the community. Accompanying this issue, albeit to a smaller magnitude, is the reviews that are categorized as "Unlike Fortnite" and "Emotes and Friends" which both highlight the playerbase's enjoyment to the unique combat movement mechanics that the game has to offer alongside its wide array of user expression within the game.
### LDA
The LDA visuals are a bit harder to interpret compared to KMeans, but we can still piece together information gathered from the various topics. 

Starting with the negative reviews. Let's first start by categorizing each of the topics here. Almost all of the topics contain general words such as "apex", "game", "play", and other such words so we'll ignore those and focus more on the unique ones for that topic. 

Starting with topic 1, we can see words such as "matchmaking", "season", "players", "servers", "money" and other words that seem to be really wide in terms of topic. We can perhaps focus on the words "money", "season", and "players" which seem to imply that the playerbase is getting affected by the recent money involved in each season, perhaps in battlepass or other microtransactions that is frequently implemented in Apex. We can then connect this to other words in the topic such as "matchmaking" and "servers" to possibly hint that players would like it more if the money invested in creating battlepass or microtransactions is instead invested in improving servers and matchmaking issues. With this, we can categorize the 1st topic as "Microtransactions".

Moving on with the 2nd topic, again, we get the same words as before such as "game", "players", "matchmaking", however, the orders are now changed. This time, we also get new words such as "time" and "hours" which may imply that players are complaining about the wait times in matchmaking, which is supported by our previous claim of matchmaking issues for the 1st topic. "Titanfall" also seems pretty high in the list, hinting that players are comparing Apex Legends to Titanfall. With these reasons, I feel that it is acceptable to classify this topic as "Wait Times".

On to the 3rd topic, we get the same words still like "servers", "players", and "money" which means these words are a really frequent topic of complaint in reviews as it is frequently a part of, or at least related to, alot of topics. We do get one new word in the mix that likely defines the topic which is "cheaters". With "players", "servers", "money", and "cheaters", we can assume that this topic pertains to the prevalence of cheaters in many servers despite the frequent game updates. It would seem that players are discontent at how the game continues to update more transactions for the players, yet could not address cheaters in lobbies. As such, we can classify this topic as "Cheaters" as I think it really defines and connects alot of the words in this topic list.

Lastly, on to the 4th topic. Unlike the other topics, this topic doesn't necessarily have any words that stand out from the rest, and like many, it contains other words that have already been mentioned by the other topics, namely "players", "servers", "time", "matchmaking", "money", and "cheaters". Seems like this topic is a mixture of all the other complaints, pointing out the major issues of the game, addressing the numerous accounts of many other reviews. So, since I have no clear assumption to classify this as, we'll categorize it as "Other".

Fortunately, we don't need to rank these as LDA has already ranked it according to the portion of the documents or tokens that the topics are pertaining to. Topic 1 has the highest, with a leading 27.8%, followed by Topic 2's 26.8%, and then Topic 3's 24.6%, and lastly Topic 4's 20.8%. This would imply that a large majority of the reviews mostly contain words that pertain to "Microtransactions" or "Wait Times" along with a bit of "Cheaters".

These assumptions fall in line with the results of our wordclouds earlier, majority of which containing the words "microtransaction", "cheater","server", and "matchmaking" for those in the negative wordcloud outputs.

The positive LDA seems to have grouped the positive reviews into 2 clusters only. Topic 1 and Topic 2 both share seemingly almost identical lists of words. Topic 1, however, has the word "movement" along with the words "battle royale" and "fun" which seem to imply that players find the unique movement of the game unlike any other battle royal they've played, which made it a really unique and fun experience for many players. Topic 2 seems to have generic words in their lists, implying that these percentage of the reviews are the generic reviews that don't really offer much depth into the game's mechanics or intrinsic characteristics, as such, these reviews are likely generic praise given as thanks to the developers of the game.

# Conclusion
From the findings we have, we can generally say that the major issues that most of the players are facing right now is the microtransactions, server issues, and the matchmaking. Players are getting really irked with the amount of microtransactions the game keeps updating and no updates fixing the recurring issues of cheaters, unfair or unbalanced matchmaking, and constant connectivity to the servers. On the other hand, the players seem to be enjoying the distinct movement mechanics of the game, allowing for some of the most dopamine-inducing gameplay that no other battle royale has ever displayed. Nevertheless, in order to regain playerbase, or better yet gain more players, the devs of the game should focus less on microtransactions and more on producing updates that address issues in matchmaking and servers. Some fix that would make matchmaking balanced by adjusting the ranks of all the players that are in the lobby and managing them so that no high-level ranks are grouped in one lobby with only a few low-level ranks. For servers, it's a more delicate matter as the matter solely relies on how the game connects to the server, so, setting up more parallel servers may reduce downtime and improve connectivity, or, having more regional-servers would likely improve server connectivity. Additionally, the devs could introduce more mobility or options in combat for the players to enjoy. They need to emphasize more flexibility and skill expression in combat to match the game's "high skill ceiling" gameplay focused on making outplays and game-changing decisions coupled with great aim.
