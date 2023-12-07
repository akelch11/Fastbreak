# Fastbreak: Retrieval Augmented Generation (RAG) for Dynamic NBA Media Content Creation

Fastbreak is a system for producing NBA media content using vector search powered RAG and LLM question answering.

Each file described:
* code: Code files (Jupyter Notebooks) for the project.
  - Article_Scraping.ipynb: For scraping news articles from nba.com/news, and inserting into nba_news_links.txt
  - Chunking_and_Embeddings.ipynb: Navigates to links in nba_news_links.txt, scrapes and chunks text according to various schema, stores in Pinecone
  - Demo.ipynb: Full RAG- question answering with supplementary image retrieval
  - Eval.ipynb: Runs full RAG-question answering system with prompts/questions from benchmark dataset, storing in json files
  - Image_Link_Embedding_and_Storage.ipynb: Embeds image metadata text and stores image links in Pinecone
  - Question_Answering.ipynb: Runs just question answering RAG system, gets text answer output only
* dataset: Files with dataset information, including scraped NBA article links, and benchmark set Q&A pairs
  - nba_news_links.txt: File of 421 article links where text was scraped and stored
  -nba_image_news_links.txt: Image links from associated articles
  - Test_Set.xlsx: Spreadsheet containing question-answer pairs of benchmark evaluation set. Also contains annotated Correct/Incorrect answers from each trial, which accuracy metrics were derived.
* question_answering_results_json: Folder of output results from each evaluation trial in JSON form
  - {chunk_type}_{embedding_type}_top{K}_test_results.json: file for output results of respective parameter combination (contains outputs for both language models) ('openai' means ada-002 embedding)
* result_spreadsheets: Folder of output results from each evaluation trial in JSON form
  - {chunk_type}_{embedding_type}_top{K}_test_results.xslx: file for output results of respective parameter combination (contains outputs for both language models) ('openai' means ada-002 embedding)
