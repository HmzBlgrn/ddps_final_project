# Diving into the Digital Public Space: A Partisanship Analysis of Twitter Search Results and For You Feeds
#### Ben Saldich, Hamza Belgroun & Harshad Gaikwad  – Spring 2024


## Table of Contents

[1. Introduction](#intro)

[2. Literature Review](#litrev)

[3. Data](#data)

[4. Analyses](#analyses)

    [4.1 Degree of Similarity of Search Results](#ana_sim)

    [4.2 Partisanship Analysis](#ana_par)

    [4.3 Topic Modeling](#ana_top_met)

[5. Limitations](#limitations)

[6. Conclusion](#conclusion)

[7. References](#bibliography)



<a name="intro"></a>
## Introduction

<p>
In the first decade of the twenty-first century, social media was expected to bring communities together. The internet had already enabled instant written communication between people living at opposite ends of the world, but social media now allowed people to participate in simultaneous social interactions within a wider community. A number of platforms offering such networks rapidly rose to prominence around this time, but very few of them garnered as much salience as Twitter.
</p>

<p>
Twitter is often referred to as a ‘digital town square’, a platform where anyone can freely express themselves to anyone else willing to engage (Yeung, 2023). By enabling individuals to express their opinions and ideas to the world using 140 (later 280) characters or less, Twitter found success as an accessible platform; its short form nature encouraged engagement, and any tweet could theoretically be seen and engaged with by any other Twitter user, irrespective of their real world communities. Twitter allowed people to instantly learn about events taking place across the world, making it a particularly useful platform in event coverage and media.
</p>

<p>
However, as social media platforms have evolved over time, research has posited that some networks favored emotionally charged content. Negative content was found to excite more emotional engagement when compared to positive and neutral content, eventually leading to offensive, polarizing, or simply false pieces of information being optimized to increase engagement of users or attract their attention (Soroka et. al, 2019; Robertson et. al, 2023a). On social media platforms today, this attention economy dictates all. Advertisers, public personalities, politicians, and social media platforms themselves attempt to attract users through their content, potentially increasing sensationalized, outrageous, and polarizing posts. 
</p>
  
<p>
When Twitter was acquired by Elon Musk in October 2022, one of his primary stated objectives was to promote free speech. Within days of his takeover, Musk fired most of the company's content moderators and the 'trust and safety' team, and reinstated the accounts of numerous personalities previously banned for toxic speech (Yeung, 2023). Under Musk’s leadership, Twitter has transformed in other ways, from blatant changes such as their rebrand as ‘X’, to more opaque tweaks to the platform’s algorithms. Anecdotal observations from users and media members alike have noted a decline in Twitter’s 'quality', while advocacy organizations have decried the proliferation of hate speech under the new leadership. In a society as politically polarized as the United States, social media platforms can play a major role in aggravating negativity on both sides of the aisle (Boxell et. al, 2022). The two major US political parties, the Democrats and the Republicans, profess polar opposite opinions on a number of major political issues. Thus, it is reasonable to expect that the engagement and feeds of party members and partisans on Twitter are equally polarizing.
</p>
  
<p>
What is less clearly understood is the impact of who one follows on one’s Twitter experience, in other words, what Twitter’s content algorithms choose to display as a result of those follows. Through our project, we intend to examine to what extent Twitter’s algorithm adapts two of its primary user feeds based on followers: the ‘For You’ feed, described by Twitter as a combination of 'accounts and Topics you follow as well as recommended posts,' and Twitter’s ‘Top’ search results, the default output of a search performed on Twitter (Twitter Help Center). Twitter has published little to no explanation to help its users understand this search results feed. Therefore, our goal is to quantify whether an account’s political affiliation (determined by the type of people they follow) has any impact on these two feeds. By creating Twitter accounts each following unique and highly partisan influencers, we compare the differing language utilized in the ‘For You’ feeds with the language employed in various search results. We hope to contribute to the understanding of the role played by Twitter in reinforcing political positions, if any. More precisely, we aim to provide an answer to two research questions:
</p>

- RQ1: How does who you follow on Twitter influence what appears in your search results?
  - Regarding RQ1, we hypothesize that Twitter provides search results that are in some way influenced by political affiliations of the accounts followed by a user.
- RQ2: Is there a political valence of search results on a political topic?
  - Regarding RQ2, we hypothesize that partisanship of search results will skew more conservatively.
  
<a name="litrev"></a>
## Literature Review
<p>
This study falls within the broader issue of the societal effects of social media algorithms, a particularly important topic given the influence of algorithms on the lives of billions. Algorithms have the capacity to induce significant, and potentially deleterious, effects at a systemic level (Lazer et al., 2023, Illing, 2018). For example, some argue that Facebook played an important role in the genocide against the Rohingya in Myanmar, in which the prioritization of engagement may have contributed to hate speech dissemination (Mozur, 2018; Lazer et al., 2023).
</p>

<p>
More specifically, although the nature of the effects identified vary, a vast literature supports the claim that users’ political views can be influenced by the content recommended by curation algorithms. Epstein and Robertson (2015) show that the ranking of search results can shift the voting preferences of undecided voters by 20% or more, a phenomenon they call the search engine manipulation effect. Notably, our study relates to a large corpora of academic research focusing on Twitter, a favored platform among academic research given the company’s generosity with user data (at least prior to Musk’s acquisition) and its widespread use among political and media ecosystems. Indeed, compared to other platforms, Twitter is often described as a privileged destination for news, in particular those related to politics (Robertson, 2023b). 
</p>

<p>
Through a study of American users of Twitter, Bail et al. (2018) argue that when exposed to opposed political ideas, users (particularly Republican users) may shift towards ideological extremes. Also focusing on the United States, Jiang et al. (2021) identify echo chambers effects, particularly among right-leaning communities. This means that, at least in certain cases, users tend to be more often exposed to opinions which are similar to theirs - which can strengthen their preexisting political opinions (Alfano et al., 2021). Though the effects of these phenomena are still debated and studied, it is clear that social media can inform and indeed shape users’ political worldviews. 
</p>

<p>
All in all, these results raise crucial questions regarding democracies and the functioning of their institutions. The fact that social media can impact citizens’ voting preferences highlights the need to better understand the political stance of the content promoted by curation algorithms, and to what extent it can vary depending on individuals’ profile and use of the platform. These are the questions around which our study revolves. 
</p>

<p>
While there has been little academic focus on Twitter’s search functionality, a recent experiment led by journalists from the Austrian newspaper Der Standard (2024) sought to understand the partisanship of the platform’s search results. Despite its important limitations, this article’s aim and methodology share some similarities with ours. Using a new email address, they created a Twitter account to try to build a setting that is as neutral as possible and get results that are not influenced by previous activity of the account. On three consecutive days, they collected the first 20 tweets from the 'Top' section of the results for four search queries ('Ukraine', 'Russia', 'Biden' and 'Trump'). Each tweet was then classified as 'Positive', 'Neutral' or 'Negative' with respect to the search query in question. 'Positive' tweets were those that support the goals and narratives of the country or politician For instance, for the 'Ukraine' query, this includes tweets which support providing the country with more weapons. On the contrary, 'Negative' tweets are those criticizing the country or politician. Lastly, tweets that are unrelated to the search term, or that do not clearly endorse a side are characterized as 'Neutral' - this includes a number of media reports. They find that the search results appear to be tilted in favor of conservatives’ positions: the tweets are significantly more positive when they relate to Trump or Russia. 67% of tweets for the 'Trump' query are positive, against only 8% for the 'Biden' query. Similarly, 'Russia' delivers 72% positive tweets against only 35% for 'Ukraine'. As mentioned above, several limitations, highlighted by the authors, weakened the scientific validity of the experiment. In particular, the samples are extremely small and the definitions of three categories are not very precise. Nonetheless, the results of this 'short experiment', as described by its authors, support the results of a Twitter-led study (Huszár et al., 2021) made before Elon Musk bought the platform. Considering the accounts of elected officials, Huszár and his colleagues assess to what extent the tweets are amplified by the platform’s algorithm. They found that, in six out of the seven countries considered (among which the United States), tweets of right-wing accounts are favored by the algorithm.
</p>

<p>
On the other hand, many Republicans believe that they are being censored by the platform. A 2020 poll reveals that 69% of Republican respondents believe that Twitter and other major tech companies favor liberals over conservatives, against 25% of Democrat pollees (Vogels et al., 2020). One of the reasons brought forward by Musk to motivate his purchase of Twitter was that, in his view, conservatives’ views were being censored by the platform (Barrett, 2022). The claim that platforms are biased against conservatives is now frequently used in the rhetoric of Republican politicians (Mosleh et al., 2024). However, Barrett and Sims (2021) conclude that no reliable large-scale study identified such bias directed against conservative content. Although Mosleh et al. (2024) find that Twitter’s right-wing users are more likely to be suspended, they demonstrate that it is linked to the fact that conservative users have a far higher probability of being bots, and that they share significantly more links to low-quality news sites, potentially related to misinformation.
</p>
  
<p>
Like many aforementioned studies, we also set our focus on the United States because this country provides an interesting case study to assess the political stance of Twitter search results. Indeed, it displays a significant level of political and ideological polarization, which keeps increasing (Perry, 2022). Americans are now greatly divided between conservatives and liberals with regard to topics such as inequality, gun control or immigration (Bail et al., 2018). Boxell et al. (2022) compare 12 OECD countries with regards to the evolution of affective polarization, which is about the tendency for partisans to dislike and distrust those from other parties (Druckman et al., 2020), and find that the United States has experienced the largest increase in polarization over the last four decades. Also considering a set of 12 Western democracies, Fletcher et al. (2020) argue that news audiences are the most polarized in the US. 
</p>

<a name="data"></a>
## Data

<p>
Our first step consisted in crafting an initial seedlist list of conservative and liberal influencers via Audiense, a social intelligence platform that uses followership data to cluster Twitter accounts. Considering two seed lists of conservative and liberal influencers, we extracted the 20,000 most engaged tweets posted in 2024 by any of these users. We then ranked these influencers along two dimensions: their number of tweets and the total amount of engagement garnered by their posts. These two scores were normalized on a [0:1] scale within three standard deviations from the mean, allowing us to clip outliers within our dataset by assigning them a maximum index of 1. We built our follower lists of conservative and liberal influencers by keeping the 100 highest-scoring influencers from each list. Manual qualitative evaluation was performed to assess the political polarity of these influencers. As predicted, these individuals published highly political, highly partisan content. One influencer appeared in both lists, a comedian whose political stance is liberal but whose 'anti-woke' comedy garners support from conservatives.
</p>
  
<p>
We then created four Twitter accounts, a conservative account (following all 100 conservative influencers), a liberal account (following all 100 liberal influencers), an account following all 199 partisan influencers (known as the 'everyone' account), and an account following no one (the 'no one' account). Before creating each account, a VPN was turned on and set to Phoenix, AZ, USA. To minimize the effect of cookies on results, each Twitter account was created using a new email account and using a “developer” browser (a web browser that provides a blank slate). In order to emulate a truly neutral profile, we selected all interest areas. Twitter requires you to follow at least 1 account, so for the ‘no one’ account, the local police dispatch Twitter account in Phoenix AZ was followed and unfollowed immediately after account creation. 
</p>

<p>
Tweets were captured using Zeeschuimer, a tool developed by the Digital Methods Initiative at the University of Amsterdam (Digital Methods Initiative, 2024). Zeeschuimer allows an individual to capture data natively as they use social media. Once accounts were created, data was collected on the ‘For You’ feeds of each profile (which combine content made by the accounts followed and other content suggested by the algorithm) to obtain, with N being the number of tweets:
</p>

<p>
- con_fy (N = 10,888)
- lib_fy (N = 11,444)
- noone_fy (N = 2,692)
- everyone_fy (N = 14,872)
</p>
  
<p>
We also collected a number of datasets using search terms. These ‘search result’ datasets were collected in tandems: two computers were set up with the same VPN set to the same location (Phoenix, AZ) and searches were executed at the same exact time using the same Wi-Fi network. In this way, the influence of timing and location-based factors on search results were minimized. Given equipment-based limitations, only two ‘search results’ datasets could be recorded at a given time. The following sets of search terms were used:   
</p>

<p align="center">
  <img width="588" alt="Screenshot 2024-05-14 at 11 15 27" src="https://github.com/bensaldich/ddps_final/assets/71343656/463053f3-1990-46a6-8475-49c13641f740">
</p>

<p>
The tweet’s body columns in our datasets were cleaned by performing lemmatization and removing stop words, URLs, and punctuation.
</p>

<a name="analyses"></a>
## Analyses

<a name="ana_sim"></a>
### Degree of Similarity of Search Results

<p>
Before determining the potential influence of followership on search results, it is first important to measure the uniqueness of search results depending on the political orientation of the account. For each pair of ‘search term’ datasets (for example, con_trumpbiden and lib_trumpbiden form a pair), a binary column was created, equal to 1 if the tweet is included in the paired dataset, and 0 if the tweet is absent from the paired dataset. The degree of equivalence in the three liberal/conservative (each associated to a search query) varies between 59.7% and 77.9%, demonstrating that a significant majority of tweets appear in both datasets for a given query.
</p>

<p align="center">
  <img width="700" alt="Screenshot 2024-05-15 at 18 59 32" src="https://github.com/bensaldich/ddps_final/assets/71343656/c0320741-e10c-4e2b-86cc-640981c0a0ee">
</p>

<p align="center">
  <img width="700" alt="Screenshot 2024-05-15 at 18 59 48" src="https://github.com/bensaldich/ddps_final/assets/71343656/788b8c74-07e0-4905-87b6-a03ce8d5d42f">
</p>

<p>
To get a more precise overview of the degree of similarity between search results, we plot the evolution of the percentage of identical tweets within a pair as the user scrolls down the tweets suggested by the algorithm. Figures 1 to 4 confirm that search results performed at the same time and in the same location (which constitute our pairs of datasets as defined above) produce relatively equivalent search results. More specifically, they all tend to suggest that the percentage is the highest within the first few hundred results, but then begin to decrease the further one scrolls in the results. In Figure 2, the proportion of equivalent results diminishes over time before beginning to increase again later in the dataset. This can, at least partially, be explained by the fact that several runs of the same search query are often necessary to collect more tweets, because the number of results is not infinite: at some point, no more tweets load and it is necessary to restart the search to gather more tweets. Lastly, it is interesting to note that the ‘immigration’ query provides results which are largely identical for both neutral accounts (the one following all influencers, and the one following no one).
</p>

<a name="ana_par"></a>
### Partisanship Analysis

<a name="ana_par_met"></a>
#### Methodology

<p>
Because our goal was to measure the influence of followership on search results, we first needed a way to quantify the partisanship of the ‘For You’ datasets. This cleaned data was scored using a scaled F-score from the Scattertext library to measure the significance of terms in between two categories (for our purposes liberal and conservative) (Kessler, 2017). This scaled F-Score balances the competing interests of high recall and precision. By combining our Conservative and Liberal 'For You' results into one dataframe, with a new column pertaining to what each tweet came from, we were able to create a partisanship corpus, with one and two-word terms and a ‘partisanship’ score measuring the degree to which that term appeared in the conservative tweets relative to the liberal tweets. This partisanship score is measured on a [0:1] scale, with terms relatively more prevalent among the conservative tweets garnering a score closer to 1. This partisanship corpus provides a measure of the significance of certain terms used more prevalently by one political affiliation in comparison to the other. Figure 1 displays the distribution of these terms, with terms more significant to liberal ‘For You’ dataset appearing towards the right of the x-axis, and terms more significant to conservative ‘For You’ dataset appearing towards the top of the y-axis. Terms that appear more frequently across both datasets appear in the top right corner of the figure. 
  </p>
  
<p align="center">
  <img width="822" alt="Screenshot 2024-05-15 at 19 04 35" src="https://github.com/bensaldich/ddps_final/assets/71343656/9f2b8ed3-2bb8-415a-a110-93bf235dacbf">
</p>

<p>
Once created, we applied those partisanship scores to the words contained in the ‘search terms’ datasets. For each tweet of each ‘search result’ data frame, we created a dictionary containing all words in that tweet that appear in the ‘For You’ term list as keys and their respective partisanship scores as their values. Because Scattertext identifies both one and two-word terms, two-word terms made up of one-word terms will have two or even three corresponding scores. Take the example of ‘joe biden’, a two-word term with a score of 0.923. This score indicates that conservatives tend to use the term ‘joe biden’ more than do liberals. However, both ‘joe’ and ‘biden’ are also included in the partisanship corpus, with two different scores, and as such, any tweet containing ‘Joe Biden’ will generate three scores, potentially distorting the results. To overcome this, we removed any one-word terms underlying two-word terms when a two-word term was present, preserving the relative partisanship score of the underlying one-word terms while prioritizing the partisanship score of two-word terms when they appear in the text.
From this dictionary, we created columns for 1) the number of terms identified in the partisanship corpus, 2) the sum of the values corresponding to  the identified terms, and 3) the sum of those scores divided by the number of terms. This final column partisanship_score will be our approximation of the relative partisanship of a given tweet. 
</p>
  
<p>
From this dictionary, we created columns for 1) the number of terms identified in the partisanship corpus, 2) the sum of the values corresponding to the identified terms, and 3) the sum of those scores divided by the number of terms. This final column partisanship_score will be our approximation of the relative partisanship of a given tweet. 
</p>
  
<p>
These columns were added to all datasets, including both the search results and the ‘For You’ datasets. We then performed additional data cleaning, removing tweets containing fewer than four identified terms to ensure that we were only scoring tweets with enough relevant data to derive a partisanship score.
</p>

<a name="ana_par_res"></a>
#### Results
  
<p>
When considering the partisanship scores recorded in the search results, a few notable results stand out. The first is that, for all but one dataset pair (the search result for Gaza, Palestine, or Israel), the average partisanship score is more conservative than liberal (Figure 6). This indicates that the text contained within the tweets provided by the search results align more closely with terms found in the conservative ‘For You’ dataset than they do with the ‘Liberal’ dataset. This was the case for both the ‘no one’ and ‘everyone’ ‘For You’ datasets, as well as the two datasets for the Trump/Biden query and the datasets for the immigration query. The one search result that displayed a neutral dataset was our ‘Gaza OR Israel OR Palestine’ query, a topic that we assumed would generate more discussion among progressive circles, but was found to have equal partisanship.
</p>
  
<p align="center">
  <img width="749" img align="center" src="https://github.com/bensaldich/ddps_final/assets/71343656/6804a132-fa78-478e-afb4-f0ac52651dc1">
</p>

<p align="center">
  Figure 6: Partisanship of Datasets Relative to Partisanship Corpus
</p>
  
<p>
The second was that, contrary to our hypothesis, search results did not appear to be influenced in any way by one’s followers. Tables 1-3 display, for each search result pair, the partisanship of the tweets found in both accounts, compared to the partisanship of the tweest found in only the liberal or conservative accounts. As demonstrated, there is very little difference between the partisanship of these groups, and no directional movement towards the partisan affiliation of a given account’s follows. 
</p>
    
<p align="center">
  <img width="845" alt="Screenshot 2024-05-15 at 19 49 16" src="https://github.com/bensaldich/ddps_final/assets/71343656/f534f755-ff8a-4f48-8ca1-720f176a505c">
</p>

<p>
Given that each ‘search result’ dataset pertains to a particular topic (immigration, Trump/Biden, or Israel/Palestine), there is no way to separate the partisanship of the words used from the partisanship of the underlying topic. This makes the partisanship of our search results more disputable. But the ‘For You’ feeds of the two neutral accounts do not display such inherent partisanship, and because of this, the slight conservative lean of both the ‘no one’ and ‘everyone’ ‘For You’ datasets suggests that Twitter might suggest slightly conservative-aligned content to a user with a 'neutral' Twitter feed (be that a feed that follow an equal mix of liberal and conservative voices, or a truly empty Twitter profile). The extent to which this phenomenon is replicable beyond our data remains to be seen, and further research will be necessary to ascertain whether this conservative preference is due to an algorithmic preference for conservative content, or a preference for more highly engaged content that happens to be conservative. 
</p>
  
<p>
Comparing the breakdown of partisanship scores within the search result pairs (Figures 7-9), we can both see the similarities of these search results (verified by the proportion of equivalent tweets shared between the pairs), as well as the relatively normal but right-leaning distribution of partisanship, with the largest proportion of tweets containing a partisanship score between 0.4–0.6.
</p>
    
<p align="center">
  <img width="250" alt="Part_dist_trump_biden" src="https://github.com/bensaldich/ddps_final/assets/71343656/6bd725c5-8d05-4a27-8bbf-91910ea25128" hspace="10">
  <img width="250" alt="Part_dist_gaza" src="https://github.com/bensaldich/ddps_final/assets/71343656/3901ec76-1302-482b-ad94-4fdfcdd22f87" hspace="10">
  <img width="250" alt="Part_dist_immigration" src="https://github.com/bensaldich/ddps_final/assets/71343656/bfcd9009-2456-4ff5-a1ec-9a196162ff49" hspace="10"><br>
</p>
<p align="center">
  Figure 7-9: Volume of Tweets by Partisanship Distribution, Search Results
</p>


<p>
Figure 10 depicts the number of identified  terms as a function of the partisanship score (following the removal of tweets containing fewer than 4 terms). It appears that the tweets coded as most liberal by and large have fewer identified  terms.  
</p>
   
<p align="center">
  <img width="350" img align="center" alt="Number of ID'd Terms" src="https://github.com/bensaldich/ddps_final/assets/71343656/b07624cf-157d-4226-b8f7-42921fe15cba">
</p>
<p align="center">
  Figure 10: Number of ID'd Terms by Partisanship Distribution
</p>

<a name="ana_top"></a>
### Topic Modeling

<a name="ana_top_met"></a>
#### Methodology
<p>
To further our understanding of the feeds, we conducted a topic modeling to characterize the extent to which topics differ between the feeds of the four accounts that we created. In order for the analysis to generate more genuine and sensible results, the columns containing the tweets’ body were cleaned, notably by removing URLs. Mentions (Twitter Help Center, 2023b) were also removed because it is not always feasible to understand the context in which they were used. Although Biden and Trump emerge frequently in our results, the associated context can be derived thanks to the many supporting words which appear along with them. This is elaborated upon in the ‘Results’ part below.
</p>

<p>
We employ BERTopic to perform the topic modeling using the ‘all-MiniLM-L6-v2’ sentence transformer. The Uniform Manifold Approximation and Production (UMAP) technique (Briggs, 2024) is applied to have more flexibility regarding the number of nearest neighbors, and modify the global and local structures accordingly. We set the parameters such that n_neighbors = 20, n_components = 5, and min_dist = 0.01 (minimum distance). Also, we use HDBSCAN clustering (Briggs, 2024) to be able to optimize the cluster size of our models. This was useful because we had targeted approximately 20 topics per dataset. This value is reached for the biggest datasets, but, for smaller ones, fewer topics emerge (with a minimum of 10 topics). The minimum cluster size was set to 20 and we have min_samples = 4. Lastly, we also use CountVectorize for the English language.
</p>

<p>
Doing so enables us to generate the bar charts representing the Topic Word Scores for each topic for a given dataset. These outputs are then analyzed in pairs, similarly to above. For instance, the conservative ‘For You’ Topic Word Score is compared with the liberal ‘For You’ Topic Word Score to identify the differences between them.
</p>

<a name="ana_top_res"></a>
#### Results  

<p>
Considering the results, a key insight is that some topics appear for both datasets within a pair. This is not surprising, because as shown above, a significant share of tweets are found in both datasets of each pair. However, the relative importance differs, since similar topics do not appear at the same position. For example, when considering the ‘conservative’ and the ‘liberal’ ‘For You’ feeds (provided as examples in Figures 6 and 7), the topic related to the Trump’s hush money case (Cabral, 2024) appears as the fourteenth topic for the former, and the third for the latter.
</p>

<p>
The ‘conservative’ ‘For You’ feed results shows that illegal immigration and free speech issues are among the most important topics, whereas, for the ‘liberal’ feed, two of the four top topics are about conflicts - Palestine/Israel and Ukraine/Russia, respectively as second and fourth topics. They do appear in the ‘conservative’ results as well, but at lower ranks (eighth and twelfth respectively). Other topics, such as gun violence and Kate Middleton’s cancer are respectively ranked as the fifth and sixth topics for the ‘liberal’ account but are not encompassed by the ‘conservative’ feed results. The opposite also happens: the topic related to trans athletes is the eleventh for the ‘conservative’ account, but does not appear for the ‘liberal’ one.
</p>

<p>
The gap is more important when analyzing the topic differences between the ‘everyone’ and ‘no one’ ‘For You’ datasets. For the former, many topics are found either in the ‘liberal’ or the ‘conservative’ accounts results. Since the ‘everyone’ account follows influencers on both sides of the political spectrum, this is not surprising. On the other hand, many of the topics for the ‘For You’ feed of the ‘no one’ account, such as NASA, Air Jordans, or Anne Hathaway are not found in any of the other three accounts' results - which was expected as well.
</p>

<p>
Considering the ‘immigration' query, made for the four accounts, it is interesting to note that a number of international matters are represented in the topic results. This is for instance the case for the Ireland immigration issue, which flared up at the period of data collection, and is prominently featured in results of all four profiles. Similarly, immigration in Canada and in the UK are topics common to all four accounts’ search results. It is the same for immigration in two African states, Nigeria and Rwanda, featured in all four datasets with very similar vocabulary. Lastly, all datasets contain a topic related to Leonel Moreno, a Venezuelan influencer who migrated to the US and made headlines around April 2024 (Price, 2024).
</p>

<p>
Lastly, for the ‘Israel/Palestine’ query, we observe very similar results with regard to the Topic Word Scores for both the liberal and conservative datasets. Although there is a slight difference in the order of topics, most of them, and the associated vocabulary, are identical.
</p>

<a name="limitations"></a>
## Limitations
<p>
There are several notable limitations that diminish the external validity of our findings. The first concerns our data collection practices. Though we collected numerous tweets for each corpus, collecting a total of 54,975 tweets across For You and search result datasets, much of the data collection occurred over a short period of time (1-2 days), making it impossible to rule out the influence of larger narratives driving the partisanship of discussion on Twitter during data collection. Further iterations of data collection and analysis would need to be conducted to diminish the influence of any one event or story on partisanship. Notably, it would be interesting to conduct a similar study with other queries than the ones considered here.
</p>
  
<p>
Other limitations concern our attempts to measure partisanship. While the scaled F-Score appears to be a good indication of term relevance in one category of text relative to another, it may have less potency on an individual tweet level. Partisanship is difficult to gauge in any form, but relying on the existence of individual terms to derive tweet-level partisanship is not perfectly accurate. In particular, our approach using Scattertext implies that sentences are considered as 'bags of words' put next to each other (Kessler, 2017) - with single words and bigrams. This enables an extensive analysis of our data, but also implies a number of hindrances (Murel and Kavlakoglu, 2024; Engati, 2024). Notably, since it only considers the frequency of occurrence, the context and word order, which can greatly affect the meaning of a sentence, are ignored.
</p>
  
<p>
This study, like others being conducted on Twitter, is also constrained by the dynamic nature of the platform. Given the company’s propensity for product change (particularly following Elon Musk’s acquisition), these results might not be relevant in a future iteration of the search results algorithm. This is worsened by the opacity of Twitter and of its algorithms, which despite Musk’s promises to bring more transparency, has increased in his era (Flam, 2023). And, although Twitter published in 2023 a snapshot of its recommendation algorithm, there is no guarantee that this is the code actually used by the company (Nicholas, 2023), since the published code is not connected to the one running on Twitter’s servers.
</p>

<a name="conclusion"></a>
## Conclusion
<p>
All in all, this research aims to contribute to a better understanding of Twitter’s algorithm. We aim to assess whether the algorithm displays political biases with regard to the content it recommends. With over 100 million users in the United States alone (Shepherd, 2024), Twitter has the potential to influence how individuals shape their political views. Therefore, studying whether its algorithm is politically neutral is very important, since the potential societal implications are profound. 
</p>

<p>
To do so, we chose to focus on the United States because the country is strongly polarized politically. After crafting two lists of influencers, respectively Democrat and Republican, we created four different accounts, with settings as neutral as possible to limit the influence of external factors. One account follows 100 liberal influencers, a second follows 100 the conservative accounts of our list, a third does not follow anyone while a fourth follows all identified influencers (both conservative and liberal). Using Zeeschuimer on these four accounts, we collect the tweets brought forward by the algorithm for the ‘For You’ feeds, and three different search queries (related to immigration, Palestine/Israel and Trump/Biden).
</p>

<p>
Through the calculation of the percentage of identical tweets between relevant pairs of dataframes (example: comparing the results of the ‘liberal’ and ‘conservative’ account for the ‘Trump/Biden’ query), we find that the accounts followed by a user do not appear to influence the search results, because the majority of the search results are identical between the two accounts. We also conduct a topic modeling analysis to have a better qualitative understanding of our data. 
</p>

<p>
Furthermore, to estimate the political stance of the results of the algorithm, we analyze the political stance of the tweets. This is done by assigning a score to the words most frequently used by Republican and Democrats (using the ‘For You’ feeds of the ‘liberal’ and ‘conservative’ account). In line with previous studies (Huszár et al., 2021; Der Standard, 2024), our results suggest that the search results are more conservative. Namely, for all but one dataset, the words contained in the search results align more closely with terms found in the ‘conservative’ ‘For You’ dataset than they do with the ‘liberal’ ‘For You’ dataset. A limitation is that each of our ‘search result’ datasets are connected to a certain topic (immigration, Trump/Biden, or Israel/Palestine) which is not neutral politically, and the partisanship related to the underlying topic cannot be separated from the partisanship of individual terms. However, the ‘For You’ feeds of the two neutral users (the ‘no one’ and ‘everyone’ accounts) also show the same tendency, even if they (in theory) have no inherent partisanship. This suggests that Twitter’s algorithm may provide content which is slightly more aligned with conservatives to ‘neutral’ users (i.e., users with an equal mix of liberals and conservatives, or an empty profile), though the extent to which this can be deemed a ‘conservative’ algorithmic preference cannot be determined given the limitations of our inquiry.
</p>

<p>
To our knowledge, our study is the first to use such methodology to empirically investigate Twitter’s search results in relation to partisanship. Despite some non-negligible limitations, our results provide valuable insights, notably because right-wing politicians now regularly claim that platforms are biased against conservatives (Mosleh et al., 2024). Further research is now required to bolster the validity of the phenomenon that our study identifies, notably by considering other search queries and investigating engagement metrics as an alternative explanation for this modest conservative slant. Indeed, it could be explained by the algorithm’s aim of providing content that will maximize user’s engagement (Nicholas, 2023), with that content happening to more often be conservative.
</p>

<a name="bibliography"></a>
## References
<p>
Alfano, M., Fard, A. E., Carter, J. A., Clutton, P., & Klein, C. (2021). Technologically scaffolded atypical cognition: The case of YouTube’s recommender system. Synthese, 199, 835-858. https://link.springer.com/article/10.1007/s11229-020-02724-x <br>
  
Bail, C. A., Argyle, L. P., Brown, T. W., Bumpus, J. P., Chen, H., Hunzaker, M. F., ... & Volfovsky, A. (2018). Exposure to opposing views on social media can increase political polarization. Proceedings of the National Academy of Sciences, 115(37), 9216-9221. https://www.pnas.org/doi/full/10.1073/pnas.1804840115 <br>

Barrett, P. M. (2022, April 20). Musk says Twitter is biased against conservatives — facts say otherwise. The Hill. https://thehill.com/opinion/technology/3273956-musk-says-twitter-is-biased-against-conservatives-facts-say-otherwise/ <br>

Barrett P. M., Sims J. G. (2021). False accusation: The unfounded claim that social media companies censor conservatives. NYU Stern Center for Business and Human Rights. https://static1.squarespace.com/static/5b6df958f8370af3217d4178/t/60187b5f45762e708708c8e9/1612217185240/NYU+False+Accusation_2.pdf  <br>

Boxell, L., Gentzkow, M., & Shapiro, J. M. (2022). Cross-country trends in affective polarization. Review of Economics and Statistics, 1-60. <br>

Briggs, J. (2024). Advanced Topic Modeling with BERTopic. Pinecone. https://www.pinecone.io/learn/bertopic/ <br>

Cabral, B. S. (2024, April 22). What to know about Trump’s hush-money trial. BBC. https://www.bbc.com/news/world-us-canada-68309680 <br>

Der Standard. (2024, March 23). Experiment: Hat der X-Algorithmus eine politische Schlagseite? DER STANDARD. https://www.derstandard.at/story/3000000212665/experiment-hat-der-x-algorithmus-eine-politische-schlagseite?ref=rss <br>

Digital Methods Initiative. (2024). Zeeschuimer. GitHub. https://github.com/digitalmethodsinitiative/zeeschuimer <br>

Druckman, J. N., Klar, S., Krupnikov, Y., Levendusky, M., & Ryan, J. B. (2020). Affective polarization, local contexts and public opinion in America. Nature Human Behaviour, 5(1), 28–38. https://doi.org/10.1038/s41562-020-01012-5 <br>

Engati. (2024). Bag of words Model. Engati. https://www.engati.com/glossary/bag-of-words <br>

Epstein, R., & Robertson, R. E. (2015). The search engine manipulation effect (SEME) and its possible impact on the outcomes of elections. Proceedings of the National Academy of Sciences of the United States of America, 112(33). https://doi.org/10.1073/pnas.1419828112 <br>

Flam, F. (2023, June 9). Musk promised transparency, then hid Twitter data. Washington Post. https://www.washingtonpost.com/business/2023/06/09/elon-musk-says-twitter-transparency-builds-trust-it-s-all-talk-no-action/b448bdc4-06b7-11ee-b74a-5bdd335d4fa2_story.html <br>

Fletcher, R., Cornia, A., & Nielsen, R. K. (2020). How Polarized Are Online and Offline News Audiences? A Comparative Analysis of Twelve Countries. The International Journal of Press/Politics, 25(2), 169-195. <br> 

Huszár, F., Ktena, S. I., O’Brien, C., Belli, L., Schlaikjer, A., & Hardt, M. (2021). Algorithmic amplification of politics on Twitter. Proceedings of the National Academy of Sciences, 119(1). https://doi.org/10.1073/pnas.2025334119 <br>

Illing, S. (2018, October 1). Algorithms are controlling your life. Vox. https://www.vox.com/technology/2018/10/1/17882340/how-algorithms-control-your-life-hannah-fry <br>

Kessler, J. S. (2017). Scattertext: a browser-based tool for visualizing how corpora differ. ArXiv Preprint. https://arxiv.org/abs/1703.00565 <br>

Lazer, D., Swire‐Thompson, B., & Wilson, C. (2023). A normative framework for assessing the information curation algorithms of the internet. Perspectives on Psychological Science. https://doi.org/10.1177/17456916231186779 <br>

McInnes, L., Healy, J., & Melville, J. (2018, February 9). UMAP: uniform manifold approximation and projection for dimension reduction. arXiv.org. https://arxiv.org/abs/1802.03426 <br>

Mosleh, M., Yang, Q., Zaman, T., Pennycook, G., & Rand, D. G. (2024). Unbiased misinformation policies sanction conservatives more than liberals. PsyArXiv Preprint. https://doi.org/10.31234/osf.io/ay9q5 <br>

Mozur, P. (2018, October 15). A Genocide Incited on Facebook, With Posts From Myanmar’s Military. The New York Times. https://www.nytimes.com/2018/10/15/technology/myanmar-facebook-genocide.html <br>

Murel, J. & Kavlakoglu, E. (2024, January 19). What is bag of words? IBM. https://www.ibm.com/topics/bag-of-words#f01 <br>

Nicholas, G. (2023, April 26). Bird’s Eye View: The limits of Twitter’s algorithm release. Center for Democracy and Technology. https://cdt.org/insights/birds-eye-view-the-limits-of-twitters-algorithm-release/ <br>

Perry, S. L. (2022). American religion in the era of increasing polarization. Annual Review of Sociology, 48(1), 87–107. https://doi.org/10.1146/annurev-soc-031021-114239 <br>

Price, S. (2024, April 3). Venezuelan “migrant influencer” who encouraged squatting under investigation for gun charges: report. Fox News. https://www.foxnews.com/politics/venezuelan-migrant-influencer-encouraged-squatting-under-investigation-gun-charges-report <br>

Robertson, C. E., Pröllochs, N., Schwarzenegger, K., Pärnamets, P., Van Bavel, J. J., & Feuerriegel, S. (2023a). Negativity drives online news consumption. Nature Human Behaviour, 7(5), 812–822. https://doi.org/10.1038/s41562-023-01538-4 <br>

Robertson, C. T. (2023b)  Here’s what our research says about news audiences on Twitter, the platform now known as X. Reuters Institute. https://reutersinstitute.politics.ox.ac.uk/news/heres-what-our-research-says-about-news-audiences-twitter-platform-now-known-x <br>

Shepherd, J. (2024, April 23). 23 Essential Twitter (X) Statistics You Need to Know in 2024. The Social Shepherd. https://thesocialshepherd.com/blog/twitter-statistics <br>

Soroka, S., Fournier, P., & Nir, L. (2019). Cross-national evidence of a negativity bias in psychophysiological reactions to news. PNAS. https://www.pnas.org/doi/epdf/10.1073/pnas.1908369116 <br>

Twitter Help Center. (2023a, October 11). About your For you timeline on X. Twitter. https://help.twitter.com/en/using-x/x-timeline <br>

Twitter Help Center. (2023b, December 12). How to post X replies and mentions. Twitter. https://help.twitter.com/en/using-x/mentions-and-replies <br>

Vogels E. A., Perrin A., & Anderson M. (2020, August 19). Most Americans think social media sites censor political viewpoints. Pew Research Center. https://www.pewresearch.org/internet/2020/08/19/most-americans-think-social-media-sites-censor-political-viewpoints/ <br>

Yeung, D. (2023, January 13). The 'Digital Town Square' problem. RAND. https://www.rand.org/pubs/commentary/2023/01/the-digital-town-square-problem.html
</p>
