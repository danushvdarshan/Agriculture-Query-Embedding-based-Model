# Embedding-Based Agricultural Query Retrieval System
      A dense vector-based semantic search system for agricultural Question–Answer pairs using transformer embeddings and FAISS.

----> Overview:

      * This project implements a retrieval-based Question Answering (QA) system for agricultural advisory queries from Tamil Nadu (India).
      * Instead of relying on keyword matching, the system uses sentence embeddings to retrieve semantically similar past queries and               return their corresponding expert responses.
      * The pipeline combines:
      * Transformer-based sentence embeddings
      * Vector similarity search using FAISS
      * NLP preprocessing
      * Threshold-based semantic filtering
      * This approach enables context-aware matching even when wording differs significantly.
      
----> Motivation:

      * Agricultural support systems often rely on historical Q&A databases. However, traditional lexical search methods fail when:
      * Farmers use different wording for similar issues
      * Spelling variations occur
      * Domain terminology varies
      * Queries are short and ambiguous
      * This project addresses these limitations by implementing dense semantic retrieval, enabling more robust and meaningful search.
      
----> System Architecture:

      The pipeline follows these steps:
      
          1) Text Preprocessing - 
                  * Lowercasing
                  * Punctuation removal
                  * Tokenization (NLTK)
                  * Lemmatization (WordNet)
                  
          2) Sentence Embedding -
                  * Model: all-MiniLM-L6-v2
                  * Library: SentenceTransformers
                  * Converts queries into dense vector representations
                  
          3) Vector Index Construction - 
                  * FAISS IndexFlatL2
                  * Stores embeddings for efficient nearest neighbor search
                  
          4) Query Retrieval - 
                  * User query is preprocessed
                  * Embedded using same transformer
                  * Top-K nearest vectors retrieved
                  * Optional similarity threshold filtering
                  
----> Tech Stack: 

      * Python
      * Pandas / NumPy
      * NLTK
      * SentenceTransformers
      * FAISS
      * scikit-learn 
      
----> Dataset:

      This project uses a subset of the Kisan Call Center (KCC) agricultural query dataset, specifically filtered for:
      Tamil Nadu state
      
      Agricultural and horticultural sectors
      Cleaned Q&A pairs
      
      Dataset Columns: 
           { BlockName
            Category
            Year
            Month
            Day
            Crop
            DistrictName
            QueryType
            Season
            Sector
            StateName
            QueryText
            KccAns }
            
      Due to computational constraints, only a single-state subset was used for local experimentation.
      Note: The dataset is used strictly for academic and research demonstration purposes.
