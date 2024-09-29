# CS 6200 Information Retrieval

Fall 2024 Semester

## Course Texts
There is no single required text for the course; however, we will refer to three different texts, and we strongly suggest following the readings from one or both of the following:

- **CMS**: Search Engines: Information Retrieval in PracticeLinks to an external site.. Croft, Metzler and Strohman (Addison-Wesley).
- **MRS**: Introduction to Information RetrievalLinks to an external site.. Manning, Raghavan, and Schütze (Cambridge).
- **CIS**: Conversational Information SeekingLinks to an external site.. Zamani, Trippas, Dalton, and Radlinski (2023 arXiv draft).

---

## Syllabus

### 1. [Overview of Information Retrieval](/workspaces/NU-Notes/CS-6200-Information-Retrieval/Lectures/cs6200-f24-1.pdf)

_Reading_: CMS chap. 1

### 2. [Architecture of a Search Engine](/workspaces/NU-Notes/CS-6200-Information-Retrieval/Lectures/cs6200-f24-2.pdf)

_Reading_: CMS ch. 2

### 3. [Acquiring Data](/workspaces/NU-Notes/CS-6200-Information-Retrieval/Lectures/cs6200-f24-3.pdf)

_Reading_: CMS chap. 3; MRS chap. 19 and 20

    - Crawling the Web
    - Document Conversion
    - Storing the Documents
    - Detecting Duplicates
    - Noise Detection and Removal

### 4. [Processing Text](/workspaces/NU-Notes/CS-6200-Information-Retrieval/Lectures/cs6200-f24-4.pdf)

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