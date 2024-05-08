## Project Documentation: Sentiment Analysis with TextBlob

### 1. Project Overview
This script performs sentiment analysis using the TextBlob library. The main goal is to process text data to determine sentiment polarity and subjectivity.

### 2. Dependencies and Setup
- **Python Libraries**:
  - `pandas` for data manipulation.
  - `textblob` for performing sentiment analysis.
  - `nltk` and `spacy` for natural language processing tasks.
- **Installation**:
  The script includes commands to install necessary libraries:
  ```bash
  pip install nltk
  pip install -U spacy
  ```

### 3. Data Loading
- **Dataset**: The script reads data from a CSV file named 'Train.csv'.
- **Reading Data**:
  ```python
  train = pd.read_csv('Train.csv')
  ```

### 4. Data Preprocessing
- **Handling Missing Values**:
  ```python
  train.dropna(inplace=True)
  ```
- **Text Cleaning Functions**:
  Includes functions to remove punctuation, special characters, URLs, numbers, and stopwords. Additionally, it performs lemmatization to bring words to their base form.
  ```python
  def remove_punctuations(text):
      ...
  def custom_remove_stopwords(text):
      ...
  def remove_special_characters(text):
      ...
  def lemmatize_text(text):
      ...
  def remove_URL(text):
      ...
  def remove_numbers(text):
      ...
  ```

### 5. Sentiment Analysis
- **Computing Sentiment**:
  Each text entry is processed to compute sentiment using TextBlob. The sentiment property of TextBlob outputs a polarity and subjectivity score.
  ```python
  train['sentiment'] = train['text'].apply(lambda tweet: TextBlob(tweet).sentiment)
  ```

### 6. Results and Interpretation
- **Output**: 9,166 reviews classified as negative, Neutral sentiments are significantly fewer, totaling only 262 instances, Positive sentiments are the least common, with merely 25 instances.
- **Discussion**: Overall, the dominance of negative sentiment underscores a potential concern that may need addressing if the dataset represents a business or service. These insights can guide further analysis to pinpoint the underlying causes and inform strategies for enhancing satisfaction or perception.

### 7. Conclusion
Summarize the effectiveness of the sentiment analysis, potential use cases, and any limitations observed during the analysis.
