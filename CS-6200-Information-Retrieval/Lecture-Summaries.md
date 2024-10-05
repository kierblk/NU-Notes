# Lecture Summaries

## Sep 30, 2024

If there are no further brief questions about the homework, please save more detailed inquiries for after class or during office hours. 
So far, we've discussed the offline components of a simple search engine architecture, which we refer to as the indexing process. 
This involves data acquisition, transformation, and the creation of data structures designed to enhance the search experience for users.

We are now transitioning to explore the query process. This involves the interaction of users with the search engine, starting with 
understanding why users are engaging with the system, known as the information need or query intent. This is distinct from the observable 
actions users take, such as typing queries or clicking on results. Our focus is on understanding the unobservable motivations behind these 
actions, such as the tasks users aim to accomplish or their pre-existing knowledge about the topic.

We categorize these information needs in various ways, such as considering how many relevant documents the user anticipates needing. This 
could range from needing a single result for a known item search, like finding a specific webpage, to needing multiple documents for 
research purposes. Additionally, the type of content users are searching for, such as text documents, videos, or specific formats like 
legal documents or patents, can vary widely.

Understanding these user intents and needs is crucial when designing search engine interfaces. It helps us infer these unobservable 
elements based on observable user actions like query inputs and interactions with search results. This understanding guides the development 
of features like query suggestions and the handling of query reformulations, where users adjust their queries in response to the results 
they receive.

We also delve into techniques for query expansion and rewriting, which involve modifying user queries to improve search results. This 
can be explicit, where users see their queries being adjusted, or implicit, where changes are made behind the scenes. Techniques like 
stemming, spelling correction, and using synonyms or related terms are employed to bridge the gap between the user's input and the 
information available in the search index.

In summary, our exploration of the query process in search engines focuses on aligning the system's capabilities with the user's 
underlying needs and intents, enhancing the effectiveness and user satisfaction of the search experience.
