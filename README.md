# okcupid
 
Data Source
-----------
The data for this project is downloadable from the Codecademy website as a [large .csv file](https://www.codecademy.com/paths/data-science/tracks/dscp-machine-learning-portfolio-project/modules/dscp-group-project-okcupid-date-a-scientist/informationals/dscp-group-project-okcupid-date-a-scientist). The file contains anonymized data in the form of text from over 59 thousand user profiles. The data include age, sex, sexual orientation, location and several essays.

Motivation
----------
I want to explore this data to see whether it is possible to divide users into clusters whose profiles are similar. I'm not so interested in sex, age, sexual orientation, location or any other type of data that would be somewhat easy to cluster. Instead, I want to focus on the words that users employ to describe themselves and their would-be partners. Each user has the opportunity to write 10 essays in their profile, and this is the data that I'm going to explore to ask the following:

- How many clusters do the profiles fall into? Are there several possible 'optimal' cluster numbers?
- Which words are most represented in each of these clusters?
- Are these words shared between clusters or are they unique?
- What do the words say about the individuals writing the profiles?

Required Libraries
------------------
- pandas
- matplotlib.pyplot
- seaborn
- nltk
- re
- sklearn
- numpy
- supervenn

Files
-----
- `LICENSE`
- `README.md` (this file)
- `date-a-scientist.ipynb` (the Jupyter Notebook that contains the code for the analysis and output graphs)
- `part_of_speech.py` (module to identify the part of speech of words to assist in lemmatization)

Methods
-------
- The text from all essays written from each individual was concatenated then de-noised and normalized. The TF-IDF algorithm employed to get a measure of word importance in each profile, then the results were clustered via the K-means algorithm. The elbow method suggests optimal cluster numbers of 12 or 16 (12 was chosen for simplicity)
- After fitting the data into 12 clusters, the 10 most common words from each cluster were found and a venn diagram was created to determine overlap between clusters
- The distribution of the 10 most common words from all clusters was then plotted as a heatmap to determine which words were present in most clusters and which words were more rare

Results
-------
- The words "love", "good" and "really" are among the top 10 in all 12 clusters
- Some clusters have substantial overlap and share up to 7 of their top 10 words, while others contain up to three unique words
- For example:
> - Clusters 10 and 11 share the words "time", "make", "love", "good", "music", "like" and "thing"
> - Only cluster 5 contains the words "travel", "try" and "new"
> - Only cluster 6 contains the words "eye", "want" and "ask"
- Only cluster 3 contains a word that can be unequivocally associated with gender ("guy")
- Some clusters seem to give more clues about the passtimes of members than others, as with cluster 5 one could imagine that these individuals enjoy travel and new experiences, while the words "play", "sport", "movie" and "work" come up in cluster 9. 

Next Steps
----------
- It would be intriguing to see whether genders or ages are overrepresented in any of these clusters. One would expect that these variables are somewhat associated with word choice, but it is not clear how much from this analysis.
