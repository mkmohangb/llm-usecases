## Semantic book recommender

  - ```data-exploration.ipynb``` - Exploration of the kaggle dataset [7k books](https://www.kaggle.com/datasets/dylanjcastillo/7k-books-with-metadata) and prepping it for model building.
  - ```vector-search.ipynb```  - implement vector search on book descriptions using OpenAI embeddings and Chroma db. Descriptions were chunked using langchain TextSplitter.
  - ```text-classification.ipynb``` - Use HF bart-large-mnli zero-shot classifier to classify books into fiction/non-fiction categories
  - ```sentiment-analysis.ipynb``` - Split the book description into sentences, use HF distilroberta model to predict the emotion for each and aggregate it.
  - ```gradio-dashboard.py``` - Dashboard that allows user to enter a textual description, category and sentiment to get a bunch of book recommendations

#### Key APIs invoked

  - numpy
    - ```np.where```
  - pandas
    - ```pd.merge``` - left join
    - ```pd.loc```
    - ```value_counts().reset_index().query("count > 50")```
    - ```books.authors.str.lower().isin(["haruki murakami"])```
    - ```books_missing_25_words[["title", "subtitle"]].astype(str).agg(": ".join, axis=1))```
   
  - chroma
    - ```similarity_search```
