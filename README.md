# Custom_TFIDF_Implementation README

Project Name: Custom TFIDF Implementation - Building a cutomary TF-IDF along with matrix feature functionality and compare with Sklearn 

# Table of Contents
1. Overview
2. Prerequisites
3. Project Structure
4. Data
5. Input
6. Model
7. Setup
8. Usage
9. Results
10. Contributing
11. License

# Overview

# Overview

This data science project is centered around the implementation of a custom TF-IDF (Term Frequency-Inverse Document Frequency) vectorizer and comparing its results with the `sklearn.feature_extraction.text.TfidfVectorizer` module. Additionally, we will explore the concept of `max_features` in the context of TF-IDF, similar to the `max_features` parameter within `TfidfVectorizer`.

The primary goal of this project is to gain a deeper understanding of TF-IDF vectorization and how it works under the hood, particularly when compared to the widely used `scikit-learn` models. We aim to strengthen our understanding of the following aspects:

- Calculating TF-IDF values for a given corpus.
- Comparing the custom TF-IDF implementation with `TfidfVectorizer`.
- Investigating the impact of limiting the number of features with `max_features`.

By undertaking this project, we aim to enhance our knowledge of natural language processing (NLP) and feature extraction techniques while gaining practical insights into the intricacies of TF-IDF. This knowledge will contribute to our proficiency in machine learning and data science.

# Prerequisites

Python 3.6 or later preferably
Jupyter Notebook
Libraries listed in requirements.txt

# Project Structure

The project structure is organized as follows: \
├──data \
├── notebooks \
│─├── CountVectorizer.ipynb \
├── README.md \
├── requirements.txt \
└── LICENSE \


# Data

## Task 2 Data

For Task 2 of this project, we employ a version-controlled approach to manage and track the data. This ensures data integrity and reproducibility throughout the project's lifecycle. We use the Data Version Control (DVC) program to maintain and version our datasets.

If you require access to the exact dataset used in Task 2, please send an email to [rathishsekhar@gmail.com](mailto:rathishsekhar@gmail.com). We will be happy to provide you with the necessary data and any additional information you may need.

We take data privacy and security seriously and handle all data requests with utmost care and compliance with relevant regulations.


# Input
For task 1 we use the sentence corpus shown as an example in the Scikit learn userguide for the sklearn.feature_extraction.TfidfVectorizer module, available at https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html as the input. 

For task 2, we input a corpus containing 746 sentences. 

# Model
1. TF-IDF


# Setup

1. Clone this repository to your local machine:
git clone https://github.com/yourusername/Custom_TFIDF_Implementation.git

2. Navigate to the project directory:
cd Custom_TFIDF_Implementation

3. Install the required Python packages:
pip install -r requirements.txt

# Usage

For exploring the tasks, refer to the jupyter notebook - notebooks/CountVectorizer.ipynb

# Ethical Considerations


This project strictly adheres to ethical guidelines and practices:

1. **No User Data Used:** We want to emphasize that no user data has been used in the development or testing of this project. We are committed to safeguarding user privacy and ensuring that any data used is anonymized and ethically sourced.

2. **For Learning Purposes:** This project is created solely for educational purposes. Our primary goal is to provide a resource for learning and understanding the inner workings of TF-IDF vectorization. We encourage responsible and ethical use of this knowledge in real-world applications.

3. **Transparency:** We are dedicated to transparency in our project's goals and functionality. We encourage open discussion and feedback to ensure that our project aligns with ethical best practices.

We welcome collaboration and contributions from the community to help improve this project's ethical stance and effectiveness.

# Results

The project achieved the following results: 
1. In task 1, the TFIDF vectors generated by both Scikit-learn and our custom code have produced exactly the same values, confirming the success of our custom implementation.
2. In task 2, we do not obtain the same vectors because, upon closer examination, it becomes evident that Scikit-learn's max_features selects features based on term frequency, whereas the features obtained through our custom implementation are ranked according to the IDF order. In the near future, we plan to write additional code to ensure that the custom feature selection process aligns with term frequency.
# Maintainance and Updates

This project is a product of continuous learning and improvement. As the author is in a learning stage, updates to the code and documentation will be made whenever time permits. 

We take pride in maintaining a comprehensive README.md document to provide users and contributors with clear instructions and insights into the project. Our goal is to make it as accessible and informative as possible.

In the future, we have plans to further enhance the project by implementing TF-IDF vectorization for a dynamic number of maximum features. This will involve sorting the features in descending order of their term frequency values, making the project even more versatile and adaptable.

Your feedback, suggestions, and contributions are highly valued. If you have ideas, encounter issues, or want to collaborate, please don't hesitate to reach out. Together, we can continue to improve and refine this project.

# Contributions
Contributions to this project are welcome. To contribute:

Fork the repository.
Create a new branch for your feature: git checkout -b feature-name
Make your changes and commit them: git commit -m 'Add feature-name'
Push to your branch: git push origin feature-name
Create a pull request.

# License

This project is licensed under the MIT License. Feel free to use and modify the code as needed.

Feel free to adapt this README template to your specific data science project. It provides a clear structure and information for users and collaborators to understand and contribute to your project effectively