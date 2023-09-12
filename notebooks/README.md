# CountVectorizer.ipynb README

# Table of Contents
1. Overview
2. What does TF-IDF mean?
3. How to compute TF-IDF?
4. Task 1
5. Task 2
<br>
<br>
# Overview
This document presents the definitions for the term "TF-IDF" and how it is calculated in scikit-learn (sklearn). Therefore, it enables the reader to understand these terms before implementing CountVectorizer.ipynb. The implementation is done through two tasks which are self explanatory. 
<br>
<br>
# What does TF-IDF mean?
<font face='georgia'>
    
   <h4><strong>What does tf-idf mean?</strong></h4>

   <p>    
Tf-idf stands for <em>term frequency-inverse document frequency</em>, and the tf-idf weight is a weight often used in information retrieval and text mining. This weight is a statistical measure used to evaluate how important a word is to a document in a collection or corpus. The importance increases proportionally to the number of times a word appears in the document but is offset by the frequency of the word in the corpus.
</p>
    
   <p>
One of the simplest ranking functions is computed by summing the tf-idf for each query term; many more sophisticated ranking functions are variants of this simple model.
</p>
    
   <p>
Tf-idf can be successfully used for stop-words filtering in various subject fields including text summarization and classification.
</p>
    
</font>


# How to compute TF-IDF?


Typically, the tf-idf weight is composed by two terms: the first computes the normalized Term Frequency (TF), aka. the number of times a word appears in a document, divided by the total number of words in that document; the second term is the Inverse Document Frequency (IDF), computed as the logarithm of the number of the documents in the corpus divided by the number of documents where the specific term appears.

 <ul>
    <li>
<strong>TF:</strong> Term Frequency, which measures how frequently a term occurs in a document. Since every document is different in length, it is possible that a term would appear much more times in long documents than shorter ones. Thus, the term frequency is often divided by the document length (aka. the total number of terms in the document) as a way of normalization: <br>

$TF(t) = \frac{\text{Number of times term t appears in a document}}{\text{Total number of terms in the document}}.$
</li>
<li>
<strong>IDF:</strong> Inverse Document Frequency, which measures how important a term is. While computing TF, all terms are considered equally important. However it is known that certain terms, such as "is", "of", and "that", may appear a lot of times but have little importance. Thus we need to weigh down the frequent terms while scale up the rare ones, by computing the following: <br>

$IDF(t) = \log_{e}\frac{\text{Total  number of documents}} {\text{Number of documents with term t in it}}.$
for numerical stabiltiy we will be changing this formula little bit
$IDF(t) = \log_{e}\frac{\text{Total  number of documents}} {\text{Number of documents with term t in it}+1}.$
</li>
</ul>

<br>
<h4><strong>Example</strong></h4>
<p>

Consider a document containing 100 words wherein the word cat appears 3 times. The term frequency (i.e., tf) for cat is then (3 / 100) = 0.03. Now, assume we have 10 million documents and the word cat appears in one thousand of these. Then, the inverse document frequency (i.e., idf) is calculated as log(10,000,000 / 1,000) = 4. Thus, the Tf-idf weight is the product of these quantities: 0.03 * 4 = 0.12.
</p>
</font>
<br>
<br>

# Task 1:
<font face='georgia'>
    <h2><strong>Building a TFIDF Vectorizer & compare its results with Sklearn:</strong></h2>

<ul>
    <li> The TFIDF vectorizer will be implemented on a collection of text documents taken from the sklearn.feature_extraction.text.TfidfVectorizer documentation (refer example).</li>
    <br>
    <li> The results of implementation of TFIDF vectorizer will be compared to that of the sklearns implemenation TFIDF vectorizer.</li>
    <br>
    <li> We realized that the Sklearn does few more tweaks in the implementation of its version of TFIDF vectorizer, so to replicate the exact results the following would be added to custom implementation of tfidf vectorizer:
       <ol>
        <li> Sklearn has its vocabulary generated from idf sroted in alphabetical order</li>
        <li> Sklearn formula of idf is different from the standard textbook formula. The constant <strong>"1"</strong> is added to the numerator and denominator of the idf as if an extra document was seen containing every term in the collection exactly once to prevent zero divisions.
            
 $IDF(t) = 1+\log_{e}\frac{1\text{ }+\text{ Total  number of documents in collection}} {1+\text{Number of documents with term t in it}}.$
        </li>
        <li> Sklearn applies L2-normalization on its output matrix.</li>
        <li> The final output of sklearn tfidf vectorizer is a sparse matrix.</li>
    </ol>
    <br>
    <li>Steps taken:
    <ol>
        <li> Fit and transform methods are written first forthecustom implementation of tfidf vectorizer.</li>
        <li> The alphabetically sorted voacb  is printed after fitting the data and is checked if its the same as that of the feature names from sklearn tfidf vectorizer. </li>
        <li> The idf values from the implementation are printed out and checked if its the same as that of sklearns tfidf vectorizer idf values. </li>
        <li> The vocab is calculated and idf values are found to be same as that of sklearns implementation of tfidf vectorizer, The following steps will be implemented. </li>
        <li> All implementations are in a sparse matrices. Before generating the final output, the sparse matrix is normalized using L2 normalization. This information has been obtained from the link: https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.normalize.html </li>
        <li> The output of the custom implementation is printed and compared with sklearns implementation of tfidf vectorizer.</li>
        <li> The output of a single document is checked in the collection of documents and then the sparse matrix related only to that document is converted into dense matrix and printed.</li>
        </ol>
<br>
<br>

  # Task 2:
  <font face='georgia'>
    <h2><strong>Implementing max features functionality:</strong></h2>

<ul>
    <li> Fit and transform functions will be modified so that the vocab will contain only 50 terms with top idf scores.</li>
    <br>
    <li>The vocabulary is limited to only top 50 features names based on their idf values i.e. that the output will have exactly 50 columns and the number of rows will depend on the number of documents in the corpus.</li>
    <br>
    <li>The corpus is loaded and used as input to the tfidf vectorizer.</li>
    <br>
    <li>Steps to approach this task:
    <ol>
        <li> The code for both fit and transform methods for the custom implementation of tfidf vectorizer will be written. Additionally, 50 features will be generated as described above.</li>
        <li> Vocabulary will be sorted in descending order of idf values and printed out. The words in the sorted vocabb after the data is fitted and therefore we obtain only the 50 terms in the vocab. The idf values for each term in the vocab is printed. </li>
        <li> All the implementations are in sparse matrices and before generating the final output, the sparse matrices are L2 normalized. Refer to this link https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.normalize.html </li>
        <li> The output of a single document is checked in the collection of documents, Later the sparse matrix related only to the document is converted into dense matrix and printed to obtain a dense matrix containing 1 row and 50 columns. </li>
        </ol>
    </li>
    <br>
   </ul>