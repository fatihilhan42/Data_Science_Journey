Text Preprocessing:

```python 
import re
from nltk.corpus import stopwords
from nltk.stem import WordNetLemmatizer

def preprocess_text(text):
    # Remove special characters and digits
    text = re.sub(r"[^a-zA-Z]", " ", text)
    
    # Convert to lowercase
    text = text.lower()
    
    # Tokenize the text
    words = text.split()
    
    # Remove stop words
    stop_words = set(stopwords.words("english"))
    words = [word for word in words if word not in stop_words]
    
    # Lemmatize words
    lemmatizer = WordNetLemmatizer()
    words = [lemmatizer.lemmatize(word) for word in words]
    
    # Join the words back into a single string
    preprocessed_text = " ".join(words)
    
    return preprocessed_text

# Example usage
text = "This is an example sentence for text preprocessing."
preprocessed_text = preprocess_text(text)
print(preprocessed_text)

```

Feature Extraction with CountVectorizer:

```python
from sklearn.feature_extraction.text import CountVectorizer

# Create an instance of CountVectorizer
vectorizer = CountVectorizer()

# Fit the vectorizer on the text data
vectorizer.fit(texts)

# Transform the text data into a matrix of token counts
X = vectorizer.transform(texts)

```

Feature Extraction with TF-IDF:

```python
from sklearn.feature_extraction.text import TfidfVectorizer

# Create an instance of TfidfVectorizer
vectorizer = TfidfVectorizer()

# Fit the vectorizer on the text data
vectorizer.fit(texts)

# Transform the text data into a TF-IDF representation
X = vectorizer.transform(texts)

```

These are just a few examples of how to handle text data. The specific techniques and approaches may vary depending on the task and the nature of the text data you are working with.
