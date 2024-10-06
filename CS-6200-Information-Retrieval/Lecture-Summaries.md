# Lecture Summaries

## Oct 3, 2024

Paraphrased Lecture Transcript:

```Text
On Monday, we discussed the concept of comparing misspelled queries with a lexicon of correctly spelled queries or previously issued queries. Simply knowing the number of changes between one query and another might not be sufficient, as context can be crucial. This idea, which dates back to the 1940s in computer science and information theory, involves the noisy channel model. Essentially, when you want to send a message, you have a query in mind and you type it, but errors can occur—mistyping, hitting the wrong keys, or forgetting spellings. In search engines, we reverse this process: given a string with errors, we infer the correct query using a model that predicts the types of errors likely to occur.

Another component we need is a language model, which predicts the kinds of queries users are likely to issue. For instance, a simple unigram model might list common words in a lexicon. A familiar example is Scrabble, where letters have points indicating their frequency in the English language. Common letters like 'E' and 'A' have lower points, while less common ones like 'X' and 'Z' have higher points. This is a unigram language model of characters. We could also consider a bigram model, which looks at the probability of one word following another.

To tackle the noisy channel problem, we use the string with errors to infer the true sequence of words the user intended. This involves the product of probabilities from the language model and the error model. For example, the probability of typing 'E' when you meant 'W' might depend on keyboard layout. If 'S' and 'A' are next to each other, the probability of mistyping one for the other is higher. We could even use a mixture model to account for different keyboards or languages.

In practice, we might start by tokenizing the query and gathering candidates for each token, looking for small edit distances. We then use the noisy channel model to select the best sequence of candidate words. We can also split and merge tokens to account for compound words or phrases.

Spelling correction is just one example of the mismatch between user intent and actual queries. Users often don't know the right terms to search for, leading to relevance feedback. This can be explicit, where users mark relevant documents, or implicit, where we assume the top results are relevant and use them to refine the query.

Pseudo-relevance feedback can improve recall but might hurt precision. Users generally prefer query suggestions, which are more transparent. Another challenge is that the same query terms can mean different things to different users, depending on context like location or previous searches. This leads to user modeling, which can be based on empirical data from query logs or more targeted data from user profiles.

Search engines also need to consider spatial information, as many queries are location-dependent. This can be inferred from document metadata or user queries. For example, a search for "movie times" might be more relevant if it includes the user's location.

After retrieving results, search engines need to present them effectively. This involves generating snippets that help users decide if a document is relevant. Snippets should include query terms and be readable. Ads are another type of result, ranked by relevance, bids, and click-through rates.

In some cases, clustering results can help users navigate large sets of results. Faceted classification, common in product search, organizes results into predefined categories. Cross-language search is another challenge, where queries and documents are in different languages. This often involves translating queries and merging results from different languages.

Finally, understanding how users interact with search engines is crucial. This involves collecting data at different levels of granularity, from detailed user studies to large-scale query logs. Observational and experimental studies can provide insights into user behavior and help improve search engine performance.
```

## Sep 30, 2024

Paraphrased Lecture Transcript:

``` Text
If there are no further questions about the homework, we can address longer questions after class or during office hours. So far, we've discussed the offline components of a simple search engine architecture, which we might call the indexing process. This involves data acquisition, transformation, and creating data structures to enhance user experience with a search engine. Now, we'll move on to the query process, where a user interacts with the system. We'll discuss how the stored documents and index interact with user queries and how logging and evaluation come into play.

We'll start by examining user interaction, which includes understanding why the user is using the system in the first place. This is known as an information need or query intent. It's important to distinguish this from what the user actually types or the actions they take, which are observable. We also need to reason about the unobservable aspects, such as the user's task, their existing knowledge, and their goals. We can categorize these information needs in various ways, such as the number of relevant documents the user thinks they need. For example, a user might be looking for a single webpage or multiple sources for research.

We also need to consider the types of documents or information the user is looking for, such as legal documents, patents, or more general information. Understanding the user's task and what they hope to accomplish can help us design better search engine interfaces. We need to infer these unobservable aspects based on observable actions, like the queries users type, the results they click on, and how long they spend on the search engine results page (SERP).

User interaction can have a direct impact on user experience. Improving ranking algorithms is important, but user interface design can have an immediate effect. We need to think about user intent and information need when designing search engine interfaces. Users often don't know exactly what they need because they are trying to fill a gap in their knowledge. This is known as the anomalous state of knowledge in search.

Most search queries are sets of keywords, which is different from more structured search interfaces used in specialized domains like legal search. For example, a paralegal might construct a complex query in Lexis, while a general user might just type a few keywords into Google. Users have been trained to use short queries, averaging about 2.3 words, because search engines haven't historically handled longer queries well.

We can help users with query selection and construction, or query reformulation. This can be explicit, like spelling correction, or implicit, like query expansion. Query expansion involves adding terms to the user's query to improve search effectiveness. We can use data to determine which terms to add, based on co-occurrence in documents or query logs.

For example, if a user searches for "tropical fish," we might expand the query with related terms like "aquarium" or "coral." We can use various association measures, like Dice's coefficient or pointwise mutual information, to find related terms. We can also use relevance feedback, where we learn from the top retrieved documents, or pseudo-relevance feedback, where we assume the top results are relevant.

Another method is using context vectors, where we represent a word by a vector of associated terms and look for nearby vectors. We can also use query logs to find related queries and expand the user's query based on what other users have searched for.

Spelling correction is a specific example of query reformulation. Many web queries contain spelling errors, and we can use edit distance to compare the user's query to a dictionary or hypothesized correct forms. The Levenshtein distance is a common measure, which counts the minimum number of insertions, deletions, substitutions, or transpositions needed to turn one string into another.

We can also use techniques like Soundex, which maps words to a phonetic code to handle variations in spelling. This was originally developed for the US census to compare last names.

In summary, we need to bridge the gap between the user's vague or incorrect queries and their actual information needs. We can use various techniques, like query expansion, relevance feedback, and spelling correction, to improve search effectiveness and user satisfaction.
```

### Lecture Key Topics

1. **Class Structure and Homework Questions:**
   - Address quick questions about homework during class.
   - Longer questions should be handled after class or during office hours.

2. **Search Engine Architecture:**
   - Covered offline components of a simple search engine architecture.
   - Discussed the indexing process, which includes data acquisition, transformation, and creating data structures to enhance user experience.

3. **Query Process:**
   - Transitioning to the query process where users interact with the information system.
   - Importance of understanding user intent or information need, separate from the actual query typed.

4. **User Intent and Information Need:**
   - Categorizing information needs based on the number of relevant documents the user expects.
   - Differentiating between single-result searches (e.g., finding a specific webpage) and open-ended research topics.

5. **User Interaction and Search Engine Interfaces:**
   - Importance of user interaction in query formulation and search results.
   - Designing search engine interfaces to bridge the gap between user intent and actual queries.

6. **Challenges in Query Formulation:**
   - Users may struggle to express their information needs due to unfamiliarity with search engines or the topic.
   - Vocabulary mismatch between user queries and expert terminology.

7. **Query Reformulation Techniques:**
   - Stemming and spelling correction to improve query accuracy.
   - Segmentation to infer structure in ungrammatical sequences of query terms.
   - Query expansion and substitution to enhance search effectiveness.

8. **Relevance Feedback and Pseudo-Relevance Feedback:**
   - Using initial search results to refine queries.
   - Assuming top results are relevant to improve search models.

9. **Association Measures for Query Expansion:**
   - Using co-occurrence analysis to find related terms.
   - Techniques like Dice's coefficient, point-wise mutual information, and chi-squared tests.

10. **Spelling Correction:**
    - Importance of correcting spelling errors in queries.
    - Techniques like Levenshtein distance to measure edit distance between words.
    - Soundex algorithm for phonetic matching.

11. **Noisy Channel Model:**
    - Combining language models and channel models to correct errors in queries.
    - Using Bayes' rule to infer the most likely intended query from the observed error string.

12. **Practical Applications:**
    - Examples of query reformulation improving search effectiveness.
    - Handling user reformulations and leveraging query logs for better search results.

13. **Algorithm Complexity:**
    - Discussing the time and space complexity of algorithms like Levenshtein distance.
    - Practical considerations for scaling these algorithms in real-world applications.

14. **Future Topics:**
    - Further exploration of vector space models and context vectors.
    - Continued discussion on the application of Bayes' rule in retrieval and query correction.

### Mind Map: Search Engine Architecture and Query Process

#### 1. Introduction

- **Questions Handling**
  - Quick questions about homework
  - Longer questions after class or in office hours

#### 2. Search Engine Architecture

- **Indexing Process**
  - Data acquisition
  - Data transformation
  - Data structure creation
  - Speeding up user experience

#### 3. Query Process

- **User Interaction**
  - User logs on and interacts
  - Store of documents
  - Index
  - Login and evaluation interaction

#### 4. User Intent and Information Need

- **Understanding User Intent**
  - Information need or query intent
  - Observable actions vs. unobservable reasons
  - Task accomplishment
  - Existing knowledge

- **Categorizing Information Needs**
  - Number of relevant documents needed
  - Single result vs. multiple results
  - Types of documents (textual, legal, patents, etc.)
  - User's task and end goal

#### 5. Observing User Behavior

- **Observable Actions**
  - Actual queries typed
  - Clicks on results
  - Time spent on results
  - Query reformulation

#### 6. Query Formulation and User Interface

- **Query Formulation**
  - Single query box
  - User interface widgets
  - Query suggestions and reformulation

- **Interaction with Search Results**
  - Search engine results page (SERP)
  - Clusters and one-box answers
  - Direct effect on user experience

#### 7. Design Challenges

- **User Intent and Information Need**
  - Bridging the gap between screen affordances and user intent
  - Anomalous state of knowledge in search

#### 8. Keyword Queries and Natural Language Queries

- **Keyword Queries**
  - Short number of keywords
  - Average query length (2.3 words)
  - Comparison with human-answered queries (30 words)

- **Query Selection and Construction**
  - Query reformulation
  - Explicit vs. implicit reformulation

#### 9. Techniques for Query Reformulation

- **Stemming and Data-Oriented Mapping**
  - Co-occurrence in query logs
  - Constructing graphs and connected components

- **Spelling Correction**
  - Common spelling errors
  - Edit distance (Levenshtein distance)
  - Soundex algorithm

- **Segmentation**
  - Inferring structure in ungrammatical sequences

- **Controlled Vocabularies**
  - Industry-specific vocabularies (e.g., Mesh thesaurus)

#### 10. Query Expansion and Rewriting

- **Automatic Query Expansion**
  - Adding terms in the background
  - Semi-automatic expansion with user feedback

- **Association Measures**
  - Point-wise mutual information
  - Expected mutual information
  - Chi-squared test

#### 11. Relevance Feedback

- **Pseudo-Relevance Feedback**
  - Learning from top retrieved documents
  - Self-training and bootstrapping

#### 12. Context Vectors

- **Vector Space Models**
  - Representing words by associated terms

#### 13. Query Logs and User Behavior

- **Using Query Logs**
  - Expanding queries based on user behavior
  - Query reformulation based on user actions

#### 14. Noisy Channel Model

- **Language Model and Channel Model**
  - Probability distribution over strings
  - Error model (edit distance)
  - Bayes' rule for inference

#### 15. Conclusion

- **Summary**
  - Importance of understanding user intent
  - Techniques for improving query formulation and expansion
  - Future directions in search engine architecture and user interaction
