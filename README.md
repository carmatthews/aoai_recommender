# Azure OpenAI Product Recommender

Implements a content-based filtering recommendation system that matches a user's request to items from a product catalog using the descriptive (textual) information. 

The first step is to generate embeddings for the textual item descriptions from the product catalog (using an Azure OpenAI embeddings model) that are referenced when a recommendation request is received.  

When a user makes a request for a recommendation, an embedding is generated for their query.  Each item in the catalog is scored based on the similarity between its embedding and the request embedding.

The recommender then uses the conversational capabilties of Azure OpenAI (ChatGPT) to provide an interactive experience for user's requesting recommendations.  The prompt to ChatGPT is enriched with a set of the top scoring similar products along with the user's question, then the conversation can flow to narrow down the set of recommendations to best for the specific situation for the user.
