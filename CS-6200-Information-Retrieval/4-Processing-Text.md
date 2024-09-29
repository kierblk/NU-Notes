# Week 4 - Processing Text Reading Summaries

## CMS Ch 4: _*"Processing Text"*_

### **4.1 From Words to Terms**

- **Key Idea**: Text transformation, or text processing, converts raw text into index terms. This includes techniques such as tokenization, stopping (removing unimportant words), and stemming (reducing words to their base form).

- **Takeaway**: The purpose of processing is to make searching more effective by focusing on meaningful words and ignoring case differences, punctuation, and other irrelevant details.

### **4.2 Text Statistics**

- **Key Idea**: Text follows predictable statistical patterns. Zipf’s law explains that a few words occur very frequently, while most words are rare. This understanding is crucial for search engines in ranking algorithms and indexing.

- **Important Figure**: _*Figure 4.1*_ shows Zipf's law, illustrating the relationship between word rank and frequency.
    ![CMS Fig 4.1](/CS-6200-Information-Retrieval/Images/CMS-Fig-4-1.png)

- **Takeaway**: Frequent words are often stopwords and are removed, while rare words can be significant for indexing. The balance of these occurrences helps search engines rank documents effectively.

### **4.2.1 Vocabulary Growth**

- **Key Idea**: Vocabulary size grows with the size of the corpus, but new word introductions decrease over time. Heaps' Law models this growth, predicting the vocabulary increase as the corpus expands.

- **Important Figure**: _*Figure 4.3*_ and _*4.4*_ show vocabulary growth graphs from collections like AP89 and GOV2.
    ![CMS Fig 4.3](/CS-6200-Information-Retrieval/Images/CMS-Fig-4-3.png)

    ![CMS Fig 4.4](/CS-6200-Information-Retrieval/Images/CMS-Fig-4-4.png)

- **Takeaway**: Even with massive corpora, new words continue to appear, which has significant implications for search engine design.

### **4.3 Document Parsing**

- **Key Idea**: Document parsing recognizes the structure and content of documents. It involves tokenizing (identifying words), handling punctuation, capitalization, and recognizing document metadata.

- **Takeaway**: Parsing turns raw documents into usable content for indexing by breaking them down into meaningful tokens, identifying phrases, and handling special elements like links and metadata.

#### **4.3.2 Tokenizing**

- **Key Idea**: Tokenizing splits the text into meaningful units, or tokens. This includes dealing with punctuation, capitalization, and special characters.

- **Takeaway**: Tokenization ensures that the terms indexed from a document match those in the user's query, preventing retrieval issues caused by discrepancies in word forms.

#### **4.3.3 Stopping**

- **Key Idea**: Stopwords (common words like "the" and "a") are removed during processing because they do not contribute to search relevance.

- **Takeaway**: Removing stopwords reduces index size and increases search efficiency, though it must be done carefully to avoid eliminating meaningful words.

#### **4.3.4 Stemming**

- **Key Idea**: Stemming reduces words to their root form to increase the likelihood of matching relevant documents. For example, "running" and "runs" both stem to "run."

- **Takeaway**: Stemming improves search effectiveness by allowing different word forms to match. Algorithmic (e.g., Porter stemmer) and dictionary-based stemming techniques are commonly used.

#### **4.3.5 Phrases and N-grams**

- **Key Idea**: Phrases (multi-word expressions) and N-grams (sequences of N words) are important for capturing meaning. These are identified and indexed during text processing.

- **Takeaway**: Identifying and indexing phrases can make retrieval more precise. N-gram models are useful for ranking documents based on multi-word terms.
  
- **Important Figure**: _*Figure 4.6*_ shows the comparison between the Porter and Krovetz stemmers, showing how different stemming approaches can affect retrieval.
    ![CMS Fig 4.6](/CS-6200-Information-Retrieval/Images/CMS-Fig-4-6.png)
  
### **4.4 Document Structure and Markup**

- **Key Idea**: Documents often contain structure and metadata, like HTML tags, which can be used to enhance search. Document structure provides hints about the importance of terms (e.g., bolded headings).

- **Important Figure**: _*Figure 4.9*_ shows the HTML structure of a web page, illustrating how elements like titles, headers, and links are parsed and used in ranking.
    ![CMS Fig 4.9](/CS-6200-Information-Retrieval/Images/CMS-Fig-4-9.png)

- **Takeaway**: Properly parsing and utilizing the structure of web pages helps search engines prioritize important content and deliver better results.