# Lecture Summaries

## THURSDAY, Sep 5, 2024

Paraphrased Lecture Transcript:

```Text
Alright, thank you for your patience. The good news is that the first class of any course often 
serves as an introduction or advertisement, explaining why the course is important and why you 
should take it. This is especially true for philosophy classes, which ask questions like "Why are 
we here?" and "Where are we going?" But for an information retrieval class, we can spend as much or 
as little time on that as we like. The short introduction to this class is simple: everyone knows 
what information retrieval is. Your grandmother knows what it is. Your family members know what 
it is. 

Information retrieval is something everyone uses. You can explain it at least at the level of the 
strategies you use to find things. Once you look at a search results page, you might start to wonder 
about the people building these pages. They are often siloed into different tasks, which can 
sometimes lead to bad interface design. For example, when you search for information retrieval, 
you might see little snippets at the top of the page. These snippets are passages of text extracted 
from documents, and we'll talk about why you might want to do that later on.

Google, for instance, might show a snippet that says, "Information retrieval is the process of 
accessing data resources." This isn't the definition we'll settle on, but it's what Google is 
advertising. They also have other elements like extracts from Wikipedia, which attempt to answer 
the question. For example, Wikipedia might say, "Information retrieval in computing and information 
science is the task of identifying and retrieving information system resources that are relevant to 
an information need." This is a bit procedural, but it gives you an idea.

There are also other interesting things on the search results page, like related searches and 
snippets from other sources. These elements try to answer the user's question in different ways. For
example, you might see links to articles about artificial intelligence, machine translation, or the 
purpose of information retrieval.

We could stop here and say, "This is an information retrieval system. Everyone knows that." But it's
useful to look at other examples to see how different systems handle information retrieval. For 
instance, if you're not logged into Google, you might get different results. This raises 
interesting questions about personalization and why it matters whether you're logged in or not.

You don't have to use Google; you can use other search engines like DuckDuckGo, which might give you
different answers. DuckDuckGo, for example, uses some of Google's resources but wraps the interface 
differently. It might show longer snippets and still have some ads, which is another interesting 
aspect of information retrieval.

Search engines often insert ads because people searching for specific things are giving information 
about what they might respond to. This makes search a good place for ads, but it also makes 
information retrieval an adversarial process, with different entities competing to capture your 
attention.

Information retrieval isn't just about search engines listing documents. It's also about trying to 
give answers and infer what question the user is asking. For example, if you search for "where can 
I grow black currants in the U.S.," the search engine has to interpret whether you're asking about 
the climate or the legality of growing black currants.

Information retrieval is also embedded in many other product categories, like shopping. If you're 
Amazon, you need an information retrieval system to help customers find what they want. Even if 
you're not going to work for Google or Microsoft, there's a long tail of information retrieval 
applications that many businesses might be interested in.

Information retrieval isn't just about web search. It's also about verticals, like searching for 
technical documentation or books. For example, Google Scholar is a vertical search engine for 
scholarly literature. It has specific metadata like authors, publication dates, and citations, which
 help users find relevant information.

In addition to these verticals, there are user interface issues, like conversational search engines.
These systems try to understand and respond to user queries in a more interactive way. For example, 
ChatGPT might give you a summary of information and then provide sources where you can learn more.

However, these systems can also make mistakes. For example, ChatGPT might confidently present 
information that isn't accurate, making it hard for users to judge the relevance of the results. 
This is a user interface fail because it makes it difficult for users to determine whether the 
information is reliable.

So, what are we doing in this course? The main goal is to help you understand search engines,
specifically how to evaluate and compare them and modify them for specific applications. Even if you
don't build a search engine from scratch, you should be able to tell when search engines are doing 
a good job.

To provide this background, we'll cover important issues in information retrieval and search 
engines. There are no required books, but there are foundational texts and more recent books on 
conversational information seeking that I recommend.

The course will be divided into two modes. The first half will adopt an architectural view, covering
the basic components of an information retrieval system. The second half will go back and swap out 
some of these basic answers for more complicated ones, building up better retrieval models and 
representations of documents.

We'll also have practical programming assignments, which will be half of the grade. These 
assignments will involve modifying starter code in Python and submitting it via GitHub. There's also
a course project, which can be done individually or in teams, where you'll design and evaluate a 
new information retrieval task.

Finally, there's a midterm exam, which will be about 20% of the grade. This exam will test your 
understanding of the basic components of an information retrieval system.

There is a late policy for assignments. You get one extension of four calendar days, not for cause, 
just because life happens. If you need more time for a specific reason, please let me know.

TAs have not been finally assigned for this class, but I'll let you know when they are. I'll also 
schedule office hours where you can come if you have questions or need help.

Now, let's try to synthesize our understanding of information retrieval into a definition. 
Information retrieval is concerned with the structure, analysis, organization, storage, searching, 
and retrieval of information. Specifically, we mean documents, which can be text, images, sound, 
video, etc.

Documents are recorded in some way and have some sort of structure. They are created with the 
intent of passing information to others. This distinguishes documents from random objects and from 
highly structured database records.

The primary factor on which information retrieval systems are evaluated is relevance. A relevant 
document contains the information that a person was looking for when they submitted a query. This 
definition acknowledges the fundamental problem of information retrieval: the user's intent is in 
their brain, and we can only infer it from the query they type.

There are many factors that influence relevance, such as the user's task, their prior knowledge,
and how much information they've already seen. We often reduce this to two dimensions: topical 
relevance and user relevance.

To evaluate information retrieval systems, we use test collections and effectiveness measures like 
precision and recall. These methods help us measure how well a system is doing its job.

In addition to these theoretical issues, there are practical issues in building a search engine, 
like building indices, scaling to large numbers of users, and filtering out bad data. We'll cover 
these topics as well.
```

## MONDAY, Sep 9, 2024

```TEXT
So, we need to discuss the entire conversation. The first homework assignment will be given out this week. I don't have a precise answer yet, but it will be distributed in the next day or so. We will discuss what you'll be doing for the first homework later in this class. We reached the point where we were discussing the issues in the information we want to cover, mainly focusing on the left side, which involves underlying research questions. For example, what does it mean for results to be relevant to users? How can we design effective ranking systems? How do we know if we're doing a good job? This involves designing protocols for testing systems, measuring users' responses, and modeling users' behavior. This is related to testing, such as what kinds of models would yield relevant results to users. As we will see later in the course, even before users see results, aspects of the design of an information retrieval system can help us gather information about what the user actually wants. This includes suggesting queries based on observed behavior or, as some of you noticed during our exercise, other behaviors we can infer from the user's computer connection or location. These are the broad research questions we will cover. We will briefly touch on some of the system questions on the right-hand side of the slide, which are important in building practical systems and vary depending on the type of system you're building. Are you building a large general-purpose web search engine, a vertical for a specific type of document in a particular industry, or something that will run on just a few kilobytes of data or ingest data from users' phones?

Given the vast number of topics we could cover, we will have to make some choices. As I mentioned in the first class, the choices we make are akin to a small-town restaurant setup, where instead of having many options for pizza places or Chinese restaurants, there might be just one of each. This metaphor illustrates that we will discuss the architecture of a search engine and note that there are many different choices we could make in implementing how we ingest text documents or represent them inside the search engine. We will mostly discuss one basic way of doing that representation and leave the more advanced methods for you to explore in your projects. This doesn't mean we will only ever talk about one way of doing something. The first part of the class will attempt to survey the architecture with the goal of being complete rather than exhaustive. Later in the second half of the class, we will revisit some of these choices.

In this first lecture, we are at a high level, covering the components we will evaluate to determine if a search engine is effective. This includes whether it provides quality results to users and how we measure that quality. We will also consider efficiency, though it is less important for this course. Let's go back to the days when IBMers in suits presented block diagrams. This is still useful for thinking about the architectural components of most information retrieval systems today. This is what we might call the query process or the online process, where the user is involved. We need to talk about users' interactions with the overall information retrieval system and with particular documents. This is online, so we need a data structure that allows us to present users with actual documents they are searching for. This is an architectural choice. You could imagine a search engine that just provides links without any information about the documents behind those links, but that would be a poor user interface. To design well, we need direct access to the actual documents the user is searching for, as well as interactions between the front-end user interface and other components like the ranking system and the evaluation model. This helps us capture and log user behavior to determine if our system is performing well and to retrain our models or improve our system choices.

Another view of the architecture, which doesn't involve the user, is the indexing process or the offline process. This is where we have all the raw material from which we want to construct a search engine, such as emails, web pages, social media posts, news articles, and office documents. This involves acquiring data, finding out what data exists, and ingesting it. For example, the web is so large and distributed that there is no central directory to get all the data from. We have to iteratively discover documents. Other data sources might have more structured ways of providing data through APIs. We will talk about this in the first and second homework assignments. Once we acquire the data, we store it in a data structure that is convenient for online interaction by users. We will briefly discuss the requirements of that data structure. We will also transform the data to make it suitable for the retrieval systems we are building. This will get more concrete in a couple of minutes. We can't just search the original documents by scanning them linearly. We need to transform the representation of these documents. The transformations might differ for web pages, emails, videos, and images. We will focus on text because it is the most widely used. These transformations will be the input to creating new data structures, generally called an index, to make interaction with an information retrieval system more efficient.

We will discuss various architectural components, such as text acquisition, which involves crawling the web to identify and get data from documents. Crawling can apply to public web documents, data warehouses, data lakes, and custom data repositories behind APIs. For web documents, knowledge of what data is out there is localized. You don't know a document exists unless another document points to it. This involves a graph-walking procedure, going from one web page to another. We need to organize this exploration to improve coverage and focus on up-to-date and high-value documents. The frequency of crawling depends on the type of document, such as the front page of the New York Times versus a hobbyist's homepage. We need to consider the properties of web pages and other data sources. We also need to convert data to common formats like XML or JSON and normalize character representations. This part used to be hard, but now there is more standardization with Unicode and UTF-8.

Besides acquiring data and normalizing formats, we need to transform the data for search procedures. This involves understanding the structure of documents, such as headings and footnotes, and breaking text into individual words. Tokenization can be hard-coded or learned from data. Modern language models use word pieces to handle new words. We might also consider stop words, which are common words like "the" that might not be useful for search. We might do further transformations to merge similar words or map sequences of words onto continuous vectors. These transformations are forms of dimensionality reduction. We might also extract metadata from documents, such as topics, domains, and languages.

After transforming the document representation, we create an index, a data structure for efficient and effective retrieval. The index depends on the retrieval model. Most indexes adapt to the statistics of the data collection and use heuristic or learned weights on features. One example is TF-IDF weighting, which combines term frequency and inverse document frequency. The fundamental idea of most indexes is inversion, mapping from terms to document positions. This can be done in various ways, depending on the retrieval model. Design considerations include updating the index, handling common words, and dealing with continuous document representations.

We will also discuss the online processes, where the user is involved. Even a text box for entering queries is a user interface. Queries are expressed in query languages, which narrow the gap between the user's query intent and the system's document representation. Query transformation improves the initial query before and after the search. This includes autocomplete, spell checking, and query expansion. User interaction also occurs after results are returned, such as showing snippets and highlighting query terms. We will discuss ranking, which involves scoring the compatibility between a query and a document. Most retrieval models use a dot product between vectors. We will also consider efficiency and distributed systems.

Finally, we will discuss evaluation, which involves measuring the relevance and efficiency of information retrieval systems. This includes collecting data from query logs and click-through logs. We will use the Text Retrieval Conference (TREC) evaluation protocol, which involves topics, descriptions, and narratives. We will create annotated data for evaluation, including relevant and non-relevant documents. This will help us evaluate the effectiveness of retrieval systems.

We will take a five-minute break and then discuss the first homework assignment, which involves creating an evaluation corpus for an information retrieval system. We will use the Chronicling America database, which contains historical newspapers. You will pick a couple of topics and create a set of relevant documents, including non-relevant documents. This will be a warm-up for the class project, which involves defining a search task and creating annotated data.

I will release the formal specification of the homework in a day or so. If you have any questions, feel free to ask. I will also update the page with office hours and TA information.
```

Paraphrased Lecture Transcript:

## THURSDAY, Sep 12, 2024

Paraphrased Lecture Transcript:

## MONDAY, Sep 16, 2024

Paraphrased Lecture Transcript:

## THURSDAY, Sep 19, 2024

Paraphrased Lecture Transcript:

## MONDAY, Sep 23, 2024

Paraphrased Lecture Transcript:

## THURSDAY, Sep 26, 2024

Paraphrased Lecture Transcript:

## MONDAY, Sep 30, 2024

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

### Key Points

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

### Conclusion

Building an effective search engine hinges on understanding and addressing the complexities of user
intent, query formulation, and result relevance. By leveraging offline indexing processes, query
reformulation techniques, and user behavior analysis, search engines can better match user needs
with relevant information. Techniques like spelling correction, query expansion, and relevance
feedback refine searches, while interfaces help bridge the gap between what users express and what
they seek. Ultimately, continual improvement in these areas enhances user experience, delivering
more accurate and efficient search results aligned with diverse information needs.

## THURSDAY, Oct 3, 2024

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

### Key Points

1. **Spelling Correction and Noisy Channel Model**:
   - Comparing misspelled queries with a lexicon of correctly spelled queries using the noisy channel model.
   - Incorporating language models (unigram, bigram) to predict query likelihood.
   - The noisy channel model helps infer the correct query from an observed error string based on information theory.

2. **Language Models**:
   - Unigram and bigram models estimate the probability of word sequences, using examples like Scrabble.
   - These models predict the likelihood of certain words following others to enhance query interpretation.

3. **Relevance Feedback and Pseudo-Relevance Feedback**:
   - Relevance feedback improves search results by leveraging user feedback on document relevance.
   - Pseudo-relevance feedback refines queries by assuming the top search results are relevant and using them to improve recall and precision.

4. **User Modeling and Context**:
   - Understanding user context (location, prior queries) enhances search relevance.
   - Aggregating user data through collaborative filtering and query logs allows for personalized and context-aware search results.

5. **Summarization and Snippets**:
   - Snippets summarize document content, helping users assess relevance without reading the entire document.
   - Effective snippets use significant words and features like query terms, headings, and sentence position.

6. **Sponsored Search and Ads**:
   - Search engines rank and display ads based on relevance, bids, and click-through rates.
   - Query expansion is crucial in ads due to their shorter text, enhancing ad visibility.

7. **Clustering and Faceted Classification**:
   - Clustering groups search results into categories for easier navigation.
   - Faceted classification, used in product searches, helps users filter results by predefined categories (e.g., Amazon).

8. **Cross-Language Search**:
   - Cross-language search addresses challenges like query and document language mismatches.
   - Techniques include query and document translation, leveraging statistical models and parallel corpora.

9. **User Studies and Data Collection**:
   - Studying user behavior via observational and experimental methods, including lab, field, and log analysis.
   - The depth and scale of data collection vary depending on the method, each with trade-offs in naturalness and flexibility.

10. **Granularity of Behavior Observation**:
    - Observing user behavior across different timeframes: micro (milliseconds), meso (minutes to days), and macro (days to months).
    - Comprehensive data collection helps in understanding user actions at various levels of granularity.

### Conclusion

Enhancing search engine performance relies on a combination of advanced techniques across spelling
correction, language modeling, and user feedback to refine queries and improve relevance.
Understanding user context and behavior is crucial in tailoring search results, while summarization
and clustering methods enhance user experience by making information more accessible. Effective use
of sponsored search, ads, and cross-language capabilities further broadens the scope and efficiency
of search systems. Comprehensive user studies and behavior observation at various granularities
provide valuable insights that drive ongoing improvements in search technology and user interaction,
laying the foundation for future developments in personalized and intelligent search systems.
