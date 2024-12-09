# Multi AI Agent system or AgenticBot


# Product(Cellphone) Recommendation System
This project builds a recommendation system for Amazon cell phones using LangChain, OpenAI, and Sentence Transformers. The system leverages product features, price, and image data to provide relevant recommendations to users.
## Table of Contents
1. **Setup and Installation**
2. **Data Loading and Preprocessing**
3. **Feature Extraction**
4. **Recommendation Agents**
  - Feature-Based Agent
  - Price-Based Agent
  - Image-Retrieval-Generaion Agent
  - Summary Agent
5. **Query Routing**
6. **Text and Image Embeddings**
7. **Product Recommendation using Sentence Transformers**
8. **Gradio Interface**
9. **Additional Testing**
## 1. Setup and Installation
This section installs the necessary libraries using `pip`:
- `langchain`, `langchain_community`, `tiktoken`, `faiss-cpu`, `gradio`, `Pillow`, `transformers`
It then imports the required libraries for data processing, machine learning, and LangChain functionality.
## 2. Data Loading and Preprocessing
- Reads the Amazon cell phone dataset (`DB_Amazon_cellphone_features.csv`).
- Prepares the data for feature extraction and recommendation.
- Sets up OpenAI API key and models (GPT-4, GPT-3.5) HuggingFace SentenceTransformers, DALLE, StableDiffusion.
## 3. Feature Extraction
- Defines a function `extract_input_features` to extract key features from product descriptions using OpenAI's chat models.
- Defines a function `recommend_similar_features` to recommend products with similar features using TF-IDF vectorization and cosine similarity.
## 4. Recommendation Agents
### Feature-Based Agent
- Creates a `features_tool` using LangChain's `Tool` to recommend products based on features.
- Initializes a `recommendation_agent` using LangChain's `initialize_agent` with the `features_tool`.
- Uses GPT-4 as the language model.
### Price-Based Agent
- Defines a function `create_price_agent` to create a price-based recommendation tool.
- Creates a `price_tool` using `create_price_agent` and Amazon cell phone data.
- Initializes a `price_agent` using LangChain's `initialize_agent` with the `price_tool`.
## 5. Query Routing
- Defines a function `route_query_to_agent` to determine which agent should handle a user query.
- Uses GPT-3.5 to route queries based on keywords related to price or features.
## 6. Text and Image Embeddings
- Preprocesses image URLs and extracts image data.
- Generates image and text embeddings using Sentence Transformers.
- Defines functions `search_feature_text` and `search_feature_image` to search for similar products using text and image embeddings.
## 7. Product Recommendation using Sentence Transformers
### Feature-Based Recommendation
- Defines a function `recommend_product_features` to recommend products based on feature similarity.
- Creates a LangChain `chain` using GPT-3.5 and a custom prompt template.
### Image-Based Recommendation
- Defines a function `recommend_image_features` to recommend products based on image similarity.
## 8. Gradio Interface
- Builds a Gradio interface to interact with the recommendation system.
- Allows users to enter queries and view product information, pros, cons, and images.
## 9. Additional Testing
- Includes various test queries to showcase the capabilities of the recommendation system.
  User prompt: "Suggest a smartphone with 16GB RAM under $800."
    Expected Output: Relevant products extracted from features and reviews, also images.
  User prompt:: "Show me laptops with 512GB SSD."
    Expected Output: Laptops meeting criteria with features and ratings and generate missing Images.

## Note
This README provides a general overview of the code. For more detailed explanations, refer to the comments within the notebook.
