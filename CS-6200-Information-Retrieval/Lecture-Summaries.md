# Lecture Summaries

## Oct 3, 2024

Paraphrased Lecture Transcript:

```Text
On Monday, we discussed the concept of comparing misspelled queries with a lexicon of correctly 
spelled queries or previously issued queries. Simply knowing the number of changes between one 
query and another might not be sufficient, as context can be crucial. This idea, which dates back 
to the 1940s in computer science and information theory, involves the noisy channel model. 
Essentially, when you want to send a message, you have a query in mind and you type it, but errors 
can occur—mistyping, hitting the wrong keys, or forgetting spellings. In search engines, we reverse 
this process: given a string with errors, we infer the correct query using a model that predicts 
the types of errors likely to occur.

Another component we need is a language model, which predicts the kinds of queries users are likely 
to issue. For instance, a simple unigram model might list common words in a lexicon. A familiar 
example is Scrabble, where letters have points indicating their frequency in the English language. 
Common letters like 'E' and 'A' have lower points, while less common ones like 'X' and 'Z' have 
higher points. This is a unigram language model of characters. We could also consider a bigram 
model, which looks at the probability of one word following another.

To tackle the noisy channel problem, we use the string with errors to infer the true sequence of 
words the user intended. This involves the product of probabilities from the language model and the 
error model. For example, the probability of typing 'E' when you meant 'W' might depend on keyboard 
layout. If 'S' and 'A' are next to each other, the probability of mistyping one for the other is 
higher. We could even use a mixture model to account for different keyboards or languages.

In practice, we might start by tokenizing the query and gathering candidates for each token, 
looking for small edit distances. We then use the noisy channel model to select the best sequence 
of candidate words. We can also split and merge tokens to account for compound words or phrases.

Spelling correction is just one example of the mismatch between user intent and actual queries. 
Users often don't know the right terms to search for, leading to relevance feedback. This can be 
explicit, where users mark relevant documents, or implicit, where we assume the top results are 
relevant and use them to refine the query.

Pseudo-relevance feedback can improve recall but might hurt precision. Users generally prefer query 
suggestions, which are more transparent. Another challenge is that the same query terms can mean 
different things to different users, depending on context like location or previous searches. This 
leads to user modeling, which can be based on empirical data from query logs or more targeted data 
from user profiles.

Search engines also need to consider spatial information, as many queries are location-dependent. 
This can be inferred from document metadata or user queries. For example, a search for 
"movie times" might be more relevant if it includes the user's location.

After retrieving results, search engines need to present them effectively. This involves generating 
snippets that help users decide if a document is relevant. Snippets should include query terms and 
be readable. Ads are another type of result, ranked by relevance, bids, and click-through rates.

In some cases, clustering results can help users navigate large sets of results. Faceted 
classification, common in product search, organizes results into predefined categories. 
Cross-language search is another challenge, where queries and documents are in different languages. 
This often involves translating queries and merging results from different languages.

Finally, understanding how users interact with search engines is crucial. This involves collecting 
data at different levels of granularity, from detailed user studies to large-scale query logs. 
Observational and experimental studies can provide insights into user behavior and help improve 
search engine performance.
```

## Sep 30, 2024

Paraphrased Lecture Transcript:

``` Text
If there are no further questions about the homework, we can address longer questions after class 
or during office hours. So far, we've discussed the offline components of a simple search engine 
architecture, which we might call the indexing process. This involves data acquisition, 
transformation, and creating data structures to enhance user experience with a search engine. Now, 
we'll move on to the query process, where a user interacts with the system. We'll discuss how the 
stored documents and index interact with user queries and how logging and evaluation come into play.

We'll start by examining user interaction, which includes understanding why the user is using the 
system in the first place. This is known as an information need or query intent. It's important to 
distinguish this from what the user actually types or the actions they take, which are observable. 
We also need to reason about the unobservable aspects, such as the user's task, their existing 
knowledge, and their goals. We can categorize these information needs in various ways, such as the 
number of relevant documents the user thinks they need. For example, a user might be looking for a 
single webpage or multiple sources for research.

We also need to consider the types of documents or information the user is looking for, such as 
legal documents, patents, or more general information. Understanding the user's task and what they 
hope to accomplish can help us design better search engine interfaces. We need to infer these 
unobservable aspects based on observable actions, like the queries users type, the results they 
click on, and how long they spend on the search engine results page (SERP).

User interaction can have a direct impact on user experience. Improving ranking algorithms is 
important, but user interface design can have an immediate effect. We need to think about user 
intent and information need when designing search engine interfaces. Users often don't know exactly 
what they need because they are trying to fill a gap in their knowledge. This is known as the 
anomalous state of knowledge in search.

Most search queries are sets of keywords, which is different from more structured search interfaces 
used in specialized domains like legal search. For example, a paralegal might construct a complex 
query in Lexis, while a general user might just type a few keywords into Google. Users have been 
trained to use short queries, averaging about 2.3 words, because search engines haven't historically 
handled longer queries well.

We can help users with query selection and construction, or query reformulation. This can be 
explicit, like spelling correction, or implicit, like query expansion. Query expansion involves 
adding terms to the user's query to improve search effectiveness. We can use data to determine 
which terms to add, based on co-occurrence in documents or query logs.

For example, if a user searches for "tropical fish," we might expand the query with related terms 
like "aquarium" or "coral." We can use various association measures, like Dice's coefficient or 
pointwise mutual information, to find related terms. We can also use relevance feedback, where we 
learn from the top retrieved documents, or pseudo-relevance feedback, where we assume the top 
results are relevant.

Another method is using context vectors, where we represent a word by a vector of associated terms 
and look for nearby vectors. We can also use query logs to find related queries and expand the 
user's query based on what other users have searched for.

Spelling correction is a specific example of query reformulation. Many web queries contain spelling 
errors, and we can use edit distance to compare the user's query to a dictionary or hypothesized 
correct forms. The Levenshtein distance is a common measure, which counts the minimum number of 
insertions, deletions, substitutions, or transpositions needed to turn one string into another.

We can also use techniques like Soundex, which maps words to a phonetic code to handle variations 
in spelling. This was originally developed for the US census to compare last names.

In summary, we need to bridge the gap between the user's vague or incorrect queries and their 
actual information needs. We can use various techniques, like query expansion, relevance feedback, 
and spelling correction, to improve search effectiveness and user satisfaction.
```

### Lecture Key Points

1. **Search Engine Architecture:**
   - Offline components of a search engine, including indexing, data acquisition, transformation, and data structure creation to enhance user experience.
   - The indexing process is critical for speeding up the search experience.

2. **Query Process:**
   - Users interact with the search engine to retrieve information, and understanding user intent (or information need) is vital.
   - Observing user behavior, such as actual queries, clicks, and query reformulation, helps refine results.

3. **User Intent and Information Need:**
   - Differentiating between user intent and the typed query, with various information needs, ranging from single-result searches to broad research topics.
   - Categorizing information needs based on the type and number of relevant documents expected by the user.

4. **User Interaction and Search Engine Interfaces:**
   - Design of search engine interfaces should bridge the gap between user intent and the query.
   - Query formulation challenges arise due to vocabulary mismatches or unfamiliarity with search engines and topics.

5. **Challenges in Query Formulation:**
   - Users may struggle to express their needs clearly, leading to potential mismatches in expected results.
   - Interfaces, such as a single search box and query suggestions, aim to assist users in formulating more effective queries.

6. **Query Reformulation Techniques:**
   - Techniques like stemming, spelling correction, segmentation, and query expansion improve search accuracy and efficiency.
   - Query expansion is enhanced through association measures like co-occurrence analysis, mutual information, and chi-squared tests.

7. **Relevance Feedback and Pseudo-Relevance Feedback:**
   - Utilizing initial search results (pseudo-relevance feedback) to refine queries and improve search models.
   - Feedback loops from top documents help optimize future search queries.

8. **Spelling Correction and the Noisy Channel Model:**
   - Addressing spelling errors in user queries using techniques such as Levenshtein distance and the Soundex algorithm for phonetic matching.
   - The noisy channel model combines language models with error models to infer user intent using Bayes' rule.

9. **Keyword and Natural Language Queries:**
   - Short keyword queries (typically 2-3 words) contrast with human-answered natural language queries.
   - Query selection and reformulation (explicit and implicit) play a role in search outcomes.

10. **Association Measures for Query Expansion:**
    - Using techniques like Dice’s coefficient, mutual information, and chi-squared tests to find related terms and improve search relevance.

11. **Context Vectors and Query Logs:**
    - Context vectors and vector space models represent words based on associations, helping refine search results.
    - Query logs provide insights into user behavior, supporting query expansion and reformulation based on observed actions.

### Conclusion: Understanding user intent and refining queries through feedback and reformulation is essential for improving search engine architecture and user interaction.
