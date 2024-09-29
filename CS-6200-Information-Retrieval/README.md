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

| Week   	|  Lectures Slides & Summaries	|   Reading	|   Topics	|
|:--:	|---	|---	|---	|
|  1 	|   [Overview of Information Retrieval](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-1.pdf)	|   CMS chap. 1	|   	|
|  2 	|   [Architecture of a Search Engine](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-2.pdf)	|   CMS ch. 2	|   	|
|  3 	|   Acquiring Data<br />[Slides](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-3.pdf)<br />[Reading Summaries](/CS-6200-Information-Retrieval/3-Aquiring-Data.md)	|   [CMS chap. 3](/CS-6200-Information-Retrieval/Texts/CMS-Ch-3.pdf)<br>MRS chap. 19 and 20	|   - Crawling the Web<br /> - Document Conversion<br /> - Storing the Documents<br /> - Detecting Duplicates<br /> - Noise Detection and Removal	|
|  4 	|   [Processing Text](/CS-6200-Information-Retrieval/Lectures/cs6200-f24-4.pdf)	|   [CMS chap. 4](CS-6200-Information-Retrieval/Texts/CMS-Ch-4.pdf)<br> MRS chap. 2 and 21	|   - Text Statistics<br />- Document Parsing<br />- Tokenizing<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Stopping<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Stemming<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Phrases<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Document Structure<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Link Extraction<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* More detail on PageRank<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Feature Extraction and Named Entity Recognition<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Internationalization	|
|  5 	|   Ranking with Indexes	|   CMS chap. 5<br />MRS chap. 4-5	|   - Abstract Model of Ranking<br />- Inverted indexes<br />- MapReduce<br />- Query Processing<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Document-at-a-time evaluation<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Term-at-a-time evaluation<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Optimization techniques<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Structured queries<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Distributed evaluation<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Caching	|
|  6 	|   Queries and Interfaces	|   CMS chap. 6	|      - Information Needs and Queries<br />- Query Transformation and Refinement<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Stopping and Stemming Revisited<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Spell Checking and Query Suggestions<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Query Expansion<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Relevance Feedback<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Context and Personalization<br />- Displaying the Results<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Result Pages and Snippets<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Advertising and Search<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Clustering the Results<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Translation<br/>- User Behavior Analysis	|
|  7 	|   Retrieval Models	|   CMS chap. 7<br />MRS chap. 11-12<br />(for background<br />ch. 1 and 6)	|   - Overview of Retrieval Models<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Boolean Retrieval<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* The Vector Space Model<br />- Probabilistic Models<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Information Retrieval as Classification<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* The BM25 Ranking Algorithm<br />- Ranking based on Language Models<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Query Likelihood Ranking<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Relevance Models and Pseudo-Relevance Feedback<br />- Complex Queries and Combining Evidence<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* The Inference Network Model<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Query Languages<br />- Models for Web search<br />- Learning to Rank (LeToR)<br />- Neural Models for Reranking<br />- Neural Models for Indexing	|
|  8 	|   Evaluating Search Engines	|   CMS chap. 8<br />MRS chap. 8	|       - Test collections<br />- Query logs<br />- Effectiveness Metrics<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Recall and Precision<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Averaging and interpolation<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Focusing on the top documents<br />- Training, Testing, and Statistics<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Significance tests<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;* Setting parameter values	|
|  9 	|   Midterm: November 7th	|   	|   	|
| 10 	|   Document Classification	|   	|   	|
| 11 	|   Clustering and Embeddings	|   	|   	|
| 12 	|   Neural Classifiers and Language Models	|   	|   	|
| 13 	|   Conversational Information Seeking	|   	|   	|
| 14 	|   Final Project Report: December ???	|   	|   	|
