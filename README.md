# Yelp Data Challenge
![Yelp](https://www.practicevelocity.com/wp-content/uploads/2016/08/yelp2.png)
----

The idea is to 1). use Natural Language Processing (NLP) technique to extract features and classify positive and negative review; 2). build a recommendation system for yelp users. Contents of each the four Jupyter Notebook files are summarized as follows. 

### 0. Download Data
Go to [Yelp Dataset Challenge](https://www.yelp.com/dataset_challenge) and download the main dataset (1.8GB tar file). After you download and un-tar the file, you are expected to see the following folder structure:
```
dataset/
                business.json
                checkin.json
                review.json
                tip.json
                user.json
```
The Challenge Dataset:

    4.1M reviews and 947K tips by 1M users for 144K businesses
    1.1M business attributes, e.g., hours, parking availability, ambience
    Aggregated check-ins over time for each of the 125K businesses
    200,000 pictures from the included businesses

Cities:

    U.K.: Edinburgh
    Germany: Karlsruhe
    Canada: Montreal and Waterloo
    U.S.: Pittsburgh, Charlotte, Urbana-Champaign, Phoenix, Las Vegas, Madison, Cleveland

### 1. Process Data
* Merge table, filter data of last two years.
* Conduct exploratory analysis,  such as rating distribution, review counts of each business

### 2. Classify positive and negative reviews
* Get NLP representation of the documents
	* Tokenization: split words by space, lower case, remove stop words and punctuation
	* Stemming and lemmatization
	* Convert documents to vectors using TF-IDF and create training and test sets
* Classify Reviews
	* Naive Bayes
	* Logistic Regression
	* Random Forest
* Identify important features (words) of positive and negative reviews
* Compare classifiers and find the best model
	* Use Cross Validation to evaluate logistic regression
	* Use Grid Search to find best predictable classifiers

### 3. Cluster users into groups and PCA
* Cluster review text data for all restaurants
	* Define feature variable and target variable
	* Get NLP representation of the documents, create training and test sets 
	* Fit K-means clustering with the training vectors and apply it to test data
* Identify common user features for each cluster
	* Sort each centroid vector to find the top 10 features
	* Go back to vectorizer object and find out what words these features corresponds to
* Use PCA to reduce dimensionality
	* Use standardized TF-IDF vectors as features 
	* Classify positive/negative reviews with PCA preprocessing
	
### 4. Build restaurant recommender
* Filter active users and create utility matrix (rows as user, columns as business, values as rating stars)
* Collaborative filtering (Item-Item similarity recommender)
* Matrix Factorization (NMF, UVD/SVD)

	
	
