# CS 6200 Information Retrieval

Fall 2024 Semester

## Course Texts
There is no single required text for the course; however, we will refer to three different texts, and we strongly suggest following the readings from one or both of the following:

- **CMS**: Search Engines: Information Retrieval in PracticeLinks to an external site.. Croft, Metzler and Strohman (Addison-Wesley).
- **MRS**: Introduction to Information RetrievalLinks to an external site.. Manning, Raghavan, and Schütze (Cambridge).
- **CIS**: Conversational Information SeekingLinks to an external site.. Zamani, Trippas, Dalton, and Radlinski (2023 arXiv draft).

---

## Syllabus

### 1. [Overview of Information Retrieval](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-1.pdf)

_Reading_: CMS chap. 1

### 2. [Architecture of a Search Engine](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-2.pdf)

_Reading_: CMS ch. 2

### 3. [Acquiring Data](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-3.pdf)

_Reading_: CMS chap. 3; MRS chap. 19 and 20

    - Crawling the Web
    - Document Conversion
    - Storing the Documents
    - Detecting Duplicates
    - Noise Detection and Removal

#### CMS Ch 3:  _*"Crawls and Feeds"*_

---

##### 3.1 Deciding What to Search

- **Key Idea**: Search engines rely heavily on the quality and relevance of the documents they index.
- **Takeaway**: The more documents indexed, the more questions the search engine can answer, but low-quality documents can burden the ranking system.

##### 3.2 Crawling the Web

- **Key Idea**: Web crawling is essential for obtaining documents for search engines. Crawling involves retrieving web pages by sending HTTP requests and storing the results.
- **Important Figure**: _*Figure 3.1*_ shows the structure of a URL, breaking it into the scheme (e.g., HTTP), hostname, and resource path.

![CMS Figure 3.1](/CS-6200-Information-Retrieval/Images/CMS-Fig-3-1.png)

- **Challenges**: Crawling involves politeness policies to avoid overwhelming servers, multi-threading to optimize speed, and adhering to rules defined in the _*robots.txt*_ file.
- **Freshness**: Search engines must regularly check for updates on web pages, using techniques like HTTP HEAD requests to avoid outdated (stale) copies of pages.

##### 3.2.4 Focused Crawling

- **Key Idea**: Focused crawling targets specific topics, optimizing for relevance. Focused crawlers use techniques such as starting from topic-relevant seed URLs.
- **Takeaway**: Vertical search engines (searching specific domains, like movies) use this strategy to avoid the irrelevant information of general web searches.

##### 3.2.5 Deep Web

- **Key Idea**: The deep web consists of areas not easily accessible to crawlers, such as private sites, pages behind forms, and dynamically generated content.
- **Takeaway**: Many valuable resources are hidden from traditional crawlers, requiring special techniques to access them.

##### 3.2.6 Sitemaps

- **Key Idea**: Sitemaps provide crawlers with lists of URLs to help index content more efficiently.
- **Important Figure**: _*Figure 3.8*_ shows an XML-based sitemap with metadata about URLs, such as modification dates and update frequencies.

##### 3.3 Crawling Documents and Email

- **Key Idea**: Desktop search tools crawl local files and email. 
- **Challenges**: Crawling desktop data requires quick indexing of new content, while managing privacy and permissions, particularly in shared networks.

##### 3.4 Document Feeds

- **Key Idea**: Document feeds, like RSS, provide new content to search engines. These feeds are updated regularly and contain structured data.
- **Important Figure**: _*Figure 3.9*_ demonstrates an RSS feed with two articles, including publish dates and content descriptions.

##### 3.5 The Conversion Problem

- **Key Idea**: Search engines must handle many incompatible file formats, converting them to a common format (usually HTML or XML).
- **Takeaway**: Accurate conversion preserves essential formatting like headings and font sizes, which aid in search result ranking.

##### 3.6 Storing the Documents

- **Key Idea**: Document storage requires efficient methods for random access, compression, and updates.
- **Important Figure**: _*Figure 3.12*_ describes BigTable, a distributed storage system used to manage large-scale document storage efficiently, highlighting its tablet-based design.

##### 3.7 Detecting Duplicates

- **Key Idea**: Detecting duplicates or near-duplicates reduces the indexing burden and improves search result relevance.
- **Important Figure**: _*Figure 3.14*_ illustrates a fingerprinting process for identifying near-duplicate documents using 3-grams and hash values.

##### 3.8 Removing Noise

- **Key Idea**: Many web pages contain extraneous content like ads or navigation links, which can degrade search quality.
- **Takeaway**: Techniques have been developed to identify the main content block on a page, ensuring the search engine focuses on relevant text for better ranking results.

---

### 4. [Processing Text](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-4.pdf)

_Reading_: CMS chap. 4; MRS chap. 2 and 21

    - Text Statistics
    - Document Parsing
        - Tokenizing
        - Stopping
        - Stemming
        - Phrases
        - Document Structure
        - Link Extraction
        - More detail on PageRank
        - Feature Extraction and Named Entity Recognition
        - Internationalization

### 5. Ranking with Indexes

_Reading_: CMS chap. 5; MRS chap. 4-5

    - Abstract Model of Ranking
    - Inverted indexes
    - MapReduce
    - Query Processing
        - Document-at-a-time evaluation
        - Term-at-a-time evaluation
        - Optimization techniques
        - Structured queries
        - Distributed evaluation
        - Caching

### 6. Queries and Interfaces

_Reading_: CMS chap. 6

    - Information Needs and Queries
    - Query Transformation and Refinement
        - Stopping and Stemming Revisited
        - Spell Checking and Query Suggestions
        - Query Expansion
        - Relevance Feedback
        - Context and Personalization
    - Displaying the Results
        - Result Pages and Snippets
        - Advertising and Search
        - Clustering the Results
        - Translation
    - User Behavior Analysis

### 7. Retrieval Models

_Reading_: CMS chap. 7; MRS chap. 11-12 and for background chap. 1 and 6

    - Overview of Retrieval Models
        - Boolean Retrieval
        - The Vector Space Model
    - Probabilistic Models
        - Information Retrieval as Classification
        - The BM25 Ranking Algorithm
    - Ranking based on Language Models
        - Query Likelihood Ranking
        - Relevance Models and Pseudo-Relevance Feedback
    - Complex Queries and Combining Evidence
        - The Inference Network Model
        - Query Languages
    - Models for Web search
    - Learning to Rank (LeToR)
    - Neural Models for Reranking
    - Neural Models for Indexing

### 8. Evaluating Search Engines

_Reading_: CMS chap. 8; MRS chap. 8

    - Test collections
    - Query logs
    - Effectiveness Metrics
        - Recall and Precision
        - Averaging and interpolation
        - Focusing on the top documents
    - Training, Testing, and Statistics
        - Significance tests
        - Setting parameter values

### 9. Midterm: November 7th

### 10. Document Classification

### 11. Clustering and Embeddings

### 12. Neural Classifiers and Language Models

### 13. Conversational Information Seeking

### 14. Final Project Report: December ???