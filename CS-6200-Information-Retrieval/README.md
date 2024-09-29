# CS 6200 Information Retrieval

**Fall 2024 Semester**

This course provides an overview of the important issues in information retrieval, and how those issues affect the design and implementation of search engine software. The course emphasizes the technology used in Web search engines and the information retrieval theories and concepts that underlie all search applications. Mathematical experience including basic probability is strongly desirable.

**Instructor**: [David Smith](http://www.ccs.neu.edu/home/dasmith), Associate Professor in Computer Science

## Course Texts
There is no single required text for the course; however, we will refer to three different texts, and we strongly suggest following the readings from one or both of the following:

- **CMS**: [Search Engines: Information Retrieval in Practice](http://www.search-engines-book.com/) Croft, Metzler and Strohman (Addison-Wesley).

- **MRS**: [Introduction to Information Retrieval](http://nlp.stanford.edu/IR-book/) Manning, Raghavan, and Schütze (Cambridge).

- **CIS**: [Conversational Information Seeking](https://arxiv.org/abs/2201.08808) Zamani, Trippas, Dalton, and Radlinski (2023 arXiv draft).

---

## Syllabus

### 1. [Overview of Information Retrieval](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-1.pdf)

_Reading_: CMS chap. 1

### 2. [Architecture of a Search Engine](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-2.pdf)

_Reading_: CMS ch. 2

### 3. [Acquiring Data](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-3.pdf)

_Reading_: [CMS chap. 3](/CS-6200-Information-Retrieval/Texts/CMS-Ch-3.pdf); MRS chap. 19 and 20

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

![CMS Fig 3.3](/CS-6200-Information-Retrieval/Images/CMS-Fig-3-3.png)

- **Freshness**: Search engines must regularly check for updates on web pages, using techniques like HTTP HEAD requests to avoid outdated (stale) copies of pages.

##### 3.2.4 Focused Crawling

- **Key Idea**: Focused crawling targets specific topics, optimizing for relevance. Focused crawlers use techniques such as starting from topic-relevant seed URLs.

    > A "topic-relevant seed URL" refers to an initial set of web addresses (URLs) selected specifically for a focused web crawler to begin its search. These URLs are chosen because they are highly relevant to the specific topic or domain the crawler is designed to explore.
    >
    > For example, if a crawler is designed to gather information about climate change, topic-relevant seed URLs might include URLs of authoritative climate research organizations, government agencies focused on environmental issues, or reputable scientific journals that frequently publish articles on climate-related topics.
    >
    >Starting from these topic-relevant seed URLs, the focused crawler follows hyperlinks to other relevant pages, allowing it to efficiently gather a body of content that aligns with the specific topic it is designed to search for. This approach helps reduce the indexing of irrelevant or off-topic content.

- **Takeaway**: Vertical search engines (searching specific domains, like movies) use this strategy to avoid the irrelevant information of general web searches.

##### 3.2.5 Deep Web

- **Key Idea**: The deep web consists of areas not easily accessible to crawlers, such as private sites, pages behind forms, and dynamically generated content.

- **Takeaway**: Many valuable resources are hidden from traditional crawlers, requiring special techniques to access them.

##### 3.2.6 Sitemaps

- **Key Idea**: Sitemaps provide crawlers with lists of URLs to help index content more efficiently.

- **Important Figure**: _*Figure 3.8*_ shows an XML-based sitemap with metadata about URLs, such as modification dates and update frequencies.

![CSM Fig 3.8](/CS-6200-Information-Retrieval/Images/CMS-Fig-3-8.png)

##### 3.3 Crawling Documents and Email

- **Key Idea**: Desktop search tools crawl local files and email.

- **Challenges**: Crawling desktop data requires quick indexing of new content, while managing privacy and permissions, particularly in shared networks.

##### 3.4 Document Feeds

- **Key Idea**: Document feeds, like RSS, provide new content to search engines. These feeds are updated regularly and contain structured data.

- **Important Figure**: _*Figure 3.9*_ demonstrates an RSS feed with two articles, including publish dates and content descriptions.

![CMS Fig 3.9](/CS-6200-Information-Retrieval/Images/CMS-Fig-3-9.png)

##### 3.5 The Conversion Problem

- **Key Idea**: Search engines must handle many incompatible file formats, converting them to a common format (usually HTML or XML).

    > Standard text file formats include raw text, RTF, HTML, XML, Microsoft Word, ODF (Open Document Format) and PDF (Portable Document Format)

- **Takeaway**: Accurate conversion preserves essential formatting like headings and font sizes, which aid in search result ranking.

##### 3.6 Storing the Documents

- **Key Idea**: Document storage requires efficient methods for random access, compression, and updates.

- **Important Figure**: _*Figure 3.12*_ describes BigTable, a distributed storage system used to manage large-scale document storage efficiently, highlighting its tablet-based design.

![CMS Fig 3.12](/CS-6200-Information-Retrieval/Images/CMS-Fig-3-12.png)

##### 3.7 Detecting Duplicates

- **Key Idea**: Detecting duplicates or near-duplicates reduces the indexing burden and improves search result relevance.

- **Important Figure**: _*Figure 3.14*_ illustrates a fingerprinting process for identifying near-duplicate documents using 3-grams and hash values.

    > The basic process of generating fingerprints is as follows:
    >
    >1. The document is parsed into words. Non-word content, such as punctuation, HTML tags, and additional whitespace, is removed (see section 4.3).
    >
    >2. The words are grouped into contiguous n-grams for some n. These are usually overlapping sequences of words (see section 4.3.5), although some techniques use non-overlapping sequences.
    >
    >3. Some of the n-grams are selected to represent the document.
    >
    >4. The selected n-grams are hashed to improve retrieval efficiency and further reduce the size of the representation.
    >
    >5. The hash values are stored, typically in an inverted index.

![CMS Fig 3.14](/CS-6200-Information-Retrieval/Images/CMS-Fig-3-14.png)

##### 3.8 Removing Noise

- **Key Idea**: Many web pages contain extraneous content like ads or navigation links, which can degrade search quality.

- **Takeaway**: Techniques have been developed to identify the main content block on a page, ensuring the search engine focuses on relevant text for better ranking results.

![CMS Fig 3.17](/CS-6200-Information-Retrieval/Images/CMS-Fig-3-17.png)

---

#### MRS Ch 19: _*"Web Search Basics"*_

##### **19.1 Background and History**

- **Key Idea**: The web is vast, decentralized, and uncoordinated, making it difficult to index effectively for search engines.

- **Takeaway**: Web search evolved from early search engines like Altavista and Yahoo, which struggled with taxonomy and scalability.

##### **19.2 Web Characteristics**

- **Key Idea**: The decentralized nature of web content creation causes significant variations in content quality, style, and trustworthiness.

- **Important Figures**:
  - _*Figure 19.1*_: Illustrates a dynamic web page created by querying a back-end database.
![MRS Fig 19.1](/CS-6200-Information-Retrieval/Images/MRS-Fig-19-1.png)

  - _*Figure 19.2*_: Shows a simple graph structure where web pages are nodes connected by directed hyperlinks.
  ![MRS Fig 19.2](/CS-6200-Information-Retrieval/Images/MRS-Fig-19-2.png)

  - _*Figure 19.4*_: Demonstrates the “bowtie” structure of the web, showing different categories (IN, OUT, SCC) and how they interconnect.
  ![MRS Fig 19.4](/CS-6200-Information-Retrieval/Images/MRS-Fig-19-4.png)

##### **19.3 Advertising as the Economic Model**

- **Key Idea**: Advertising fuels web search, with models like CPM (cost per mil) and CPC (cost per click) being foundational.

- **Takeaway**: Sponsored search is a profitable model, but click fraud (or click spam) is a significant challenge for advertisers and search engines.

- **Important Figures**:
  - _*Figure 19.6*_: Displays a typical search results page with both organic and sponsored search results.
  ![MRS Fig 19.6](/CS-6200-Information-Retrieval/Images/MRS-Fig-19-6.png)

##### **19.4 The Search User Experience**

- **Key Idea**: Understanding user intent is critical for search engines to provide relevant results. Users generally fall into three categories:
    1. **Informational queries**: Informational queries seek general information on a broad topic, such as leukemia or Provence. There is typically not a single web page that contains all the information sought; indeed, users with informational queries typically try to assimilate information from multiple web pages.

    2. **Navigational queries**: seek the website or home page of a single entity that the user has in mind, say Lufthansa airlines. In such cases, the user’s expectation is that the very ﬁrst search result should be the home page of Lufthansa. The user is not interested in a plethora of documents containing the term Lufthansa; for such a user, the best measure of user satisfaction is precision at 1.

    3. **Transactional queries**: is one that is a prelude to the user performing a transaction on the Web – such as purchasing a product, downloading a ﬁle or making a reservation. In such cases, the search engine should return results listing services that provide form interfaces for such transactions.

- **Takeaway**: Search engines prioritize relevance, precision, and simplicity to provide a fast, user-friendly experience.

- **Important Figures**:
  - _*Figure 19.7*_: Presents the architecture of a web search engine, highlighting the relationship between the crawler, indexer, and the web.
  ![MRS Fig 19.7](/CS-6200-Information-Retrieval/Images/MRS-Fig-19-7.png)

##### **19.5 Index Size and Estimation**

- **Key Idea**: Estimating the size of a search engine’s index is complicated by factors like dynamic pages and duplicate content.

- **Takeaway**: The capture-recapture method is a common approach for estimating the relative sizes of search engine indexes, though it has limitations.

#####  **19.6 Near-Duplicates and Shingling**

- **Key Idea**: The web contains many near-duplicate pages, and search engines need efficient methods to detect and remove these from their indexes.

- **Important Figures**:
  - _*Figure 19.8*_: Shows how to use shingling and hashing to detect near-duplicate documents efficiently.
  ![MRS Fig 19.8](/CS-6200-Information-Retrieval/Images/MRS-Fig-19-8.png)

---

#### MRS Ch 20: _*"Web Crawling and Indexes"*_

##### **20.1 Overview**

- **Key Idea**: Web crawling is the process of systematically gathering web pages to index for a search engine. Crawlers need to be efficient, polite, and scalable.

- **Takeaway**: Crawlers must avoid traps, respect server restrictions, and gather high-quality pages to make search engines effective.

##### **20.1.1 Features a Crawler Must Provide**

- **Key Features**: Crawlers must be robust (avoid traps), polite (respect server rules), distributed, scalable, and ensure freshness of indexed content.
  
##### **20.2 Crawling**

- **Key Idea**: Crawlers operate by starting with a set of seed URLs and traversing the web graph by fetching pages, extracting links, and queuing new URLs.

- **Important Figures**:
  - _*Figure 20.1*_: Depicts the basic crawler architecture, highlighting the flow from fetching a URL to parsing the page and updating the URL frontier.
  ![MRS Fig 20.1](/CS-6200-Information-Retrieval/Images/MRS-Fig-20-1.png)

  - _*Figure 20.2*_: Shows a distributed crawler architecture, where nodes cooperate to divide the web crawling workload.
  ![MRS Fig 20.2](/CS-6200-Information-Retrieval/Images/MRS-Fig-20-2.png)

##### **20.2.1 Crawler Architecture**

- **Key Idea**: The architecture includes modules like a URL frontier, DNS resolver, fetcher, and a duplicate elimination module to efficiently process URLs and web pages.

##### **20.2.2 DNS Resolution**

- **Key Idea**: DNS resolution is often a bottleneck in web crawling, so caching DNS lookups and implementing asynchronous DNS resolution are common strategies to enhance performance.

---

### 4. [Processing Text](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-4.pdf)

_Reading_: [CMS chap. 4](CS-6200-Information-Retrieval/Texts/CMS-Ch-4.pdf); MRS chap. 2 and 21

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