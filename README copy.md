# Master's thesis: Measuring Mass Ideological Polarisation in Multiparty Political Systems: Application in the French Context
by Oliver Norton 

In this respository you can read the code which I used to do my master's thesis. Sensitive information has been removed. The code used here is a combination of my own code, and some from a toolkit published by:

Martin-Gutierrez, S., Losada, J. C., & Benito, R. M. (2023). Multipolar social systems: Measuring polarization beyond dichotomous contexts. Chaos, Solitons & Fractals, 169, 113244.

The thesis is not publicly available, however the code here and this readme will help explain the processed involved, from collection to analysis. Since a lot of code has been removed, not all file names correspond to exactly what are in the scripts. 

## Step 1: Data collection

Twitter data is collected from a proprietary API over a period of a few days. The data is collected by minute, hour and day according to the rate limit of the API. The collected data, which is an enriched table of Tweets data (including Twitter handle, time, text, retweets etc) is stored in pickle files.

The data is collected from an analytics platform based on a saved query of keywords with boolean operators. For example, a query about US politics may be the following:

("donald trump" OR "trump" OR "elections") AND ("2024" OR "2023" OR "US" OR "United States")

Twitter posts that contain the above keywords, as well as fulfilling set parameters (e.g. Tweet created between 2023-10-10 and 2023-10-11), will be collected.

insert image: ./images/tweets_day.png

## Step 1: Data processing 

The collected data contains a lot of redundant data, and so excess columns are removed. The now smaller pickle files are stored in a separate folder, and then combined into a single file.

## Step 2: Keyword expansion 

Step 01 is initially conducted with a limited list of keywords based on field knowledge. However, for the purposes of the thesis, a more comprehensive list is needed. To find more keywords for which to search for Tweets, we use an approach called 'keyword expansion'. Keyword expansion is Natural Language Processing (NLP) technique which assesses which words co-occur together or appear in similar contexts. The code used is based on the approach used by: 

King, G., Lam, P., & Roberts, M. E. (2017). Computer-assisted keyword and document
set discovery from unstructured text. American Journal of Political Science,
61 (4), 971–988.

Using this approach, more keywords can be found.

Steps 1, 2 and 3 are repeated until there is a suitable dataset.

insert image: ./images/keyword_expansion.png

## Step 4: 

The initial analysis involves collecting basic descrptive statistics on the dataset and identifying and filtering out 'opinion leaders' or elite actors whose Tweets are influential in the dataset (and more broadly, in the context of the French elections). The main analysis uses the dataset and these elite actors to measure political polarisation between political parties during the 2022 French elections. 

insert image: ./images/vis_1.png


insert image: ./images/vis_2.png










