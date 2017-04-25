# @realDonaldTrump's top mentions

I wanted to run a meaningful analysis of @realDonaldTrump's frequently used words when he was tweeting as presidential candidate, president-elect and president.

Here's how I did it. (And <a href="https://alexandrama.github.io/trump-frequent-mentions/">here's what I found out</a>.)

<i>Scraping and cleaning tweets:</i>
- Got Twitter oAuth access via <a href="https://apps.twitter.com/">apps.twitter.com</a>
- Ran scraping package in R using stringr, twitteR, etc. for further analysis. <a href="https://github.com/alexandrama/scraping-for-twitter-mentions/blob/master/twitterScraper.R">Here's the script I used</a>.
- After running the package with two separate packages and Twitter API keys, I found that the package/Twitter API failed to get the complete collection of tweets I wanted: not only did it not scrape 3,200 tweets, it also left out numerous tweets from certain time periods (for example, tweets between 29 September and 5 October 2016 were completely missing).
- I then ran a Python script <a href="https://github.com/bpb27/twitter_scraping">forked from bpb27</a> with a separate Twitter API key, to see if my scrape would be better. All the scripts I used can be found in my <a href="https://github.com/alexandrama/twitter_scraping">fork of bpb27's repo</a>, and I've <a href="https://github.com/alexandrama/scraping-for-twitter-mentions/blob/master/pythonScrapingScript">pasted the scripts from my scrape</a> in part 1 of this repo.
- Oddly enough, tweets were also missing in this package (those between 11 March and 15 March 2017, for instance, were completely missing from this scrape). At this point I started to think it was my Twitter API keys, rather than the scripts, acting up. Sad!
- To resolve this issue, I merged the data from both the R and Python scrapes, and removed the duplicates to get the final collection. Due to many different special characters present, I had to manually sort through every tweet again to find duplicates.
- I divided the data from the final dataset into three time frames: tweets as candidate, from 6 Oct 2016 to 8 Nov 2016; as president-elect from 9 November 2016 to 20 January 2017; as president from 20 January 2017 to 15 March 2017. This gave me 160 days' worth of tweets to examine. The csv files are in part 2 of this repo, <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/2.%20raw_tweetsAsCandidate.csv">here</a>, <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/2.%20raw_tweetsAsPeotus.csv">here</a> and <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/2.%20raw_tweetsAsPotus.csv">here</a>.

<i>Examining data</i>
- Ran text mining and wordcloud programmes on the scraped tweets, now sorted into separate csv files according to the time frame. I found <a href="https://eight2late.wordpress.com/2015/05/27/a-gentle-introduction-to-text-mining-using-r/">eight2late's tutorial</a> the clearest and the most useful guide.
- The scripts are in part 3 of this repo, or <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/3.%20tm_tweetsAsCandidate.R">here</a>, <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/3.%20tm_tweetsAsPeotus.R">here</a> and <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/3.%20tm_tweetsAsPotus.R">here</a>.
- Downloaded data as csv files for further cleaning and analysis. The cleaned files are in part 4 of this repo, or here: top words as <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/4.%20wordsAsCandidate.csv">Candidate</a>, as <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/4.%20wordsAsPeotus.csv">President-elect</a> and as <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/4.%20wordsAsPotus.csv">President</a>.
- Created separate Excel file highlighting mentions of the media (e.g. "news", "fake", "nytimes") during these three time periods. <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/4.%20media%20mentions.xlsx">Here it is</a>.

<i>Presenting data</i>
- Ran ggplot scripts to visualise top mentions per period. The scripts are in part 5 of this repo: <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/5.%20plot_wordsAsCandidate.R">here</a>, <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/5.%20plot_wordsAsPeotus.R">here</a> and <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/5.%20plot_wordsAsPotus.R">here</a>. The final jpegs of the graphs are <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/wordsAsCandidate_Rplot.jpeg">here</a>, <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/wordsAsPeotus_Rplot.jpeg">here</a> and <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/wordsAsPotus_Rplot.jpeg">here</a>.
- Created interactive presentation of the graphs: <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/6.%20topMentions.js">script here</a>.
- Created interactive line graph via JavaScript and Highcharts documentation to visualise mentions of the media during each period: <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/6.%20media.js">script here</a>.

<i>The finishing touches</i>
- <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/7.%20index.html">HTML and JavaScript here</a>
- <a href="https://github.com/alexandrama/scraping-twitter-for-mentions/blob/master/7.%20style.css">CSS here</a>
- <a href="https://alexandrama.github.io/trump-frequent-mentions/">And here's the final thing!</a>
