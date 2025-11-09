#RAG-Based AI Teaching Assistant

📝 ##Overview
The RAG-Based AI Teaching Assistant is an intelligent, domain-specific chat application designed to provide accurate, real-time, and contextually grounded answers to student queries.

Unlike traditional Large Language Models (LLMs) that rely only on their pre-trained knowledge, this system utilizes the Retrieval-Augmented Generation (RAG) architecture. This approach ensures that all responses are grounded in a verified knowledge base (e.g., lecture notes, textbooks, scientific papers), significantly minimizing "hallucinations" and providing source attribution for educational verification.

Key Benefits
Accuracy & Reliability: Responses are derived directly from course materials, not general web knowledge.

24/7 Availability: Provides instant support and clarification outside of classroom hours.

Source Attribution: Students can verify the AI's answers by checking the retrieved source documents.

🧠 ##Architecture: Retrieval-Augmented Generation (RAG)
The system is built on a standard RAG pipeline, which involves three main stages: Indexing, Retrieval, and Generation.

Core Components
Knowledge Base/Data Ingestion: Course documents (PDFs, Markdown, text files) are loaded, parsed, and split into small, manageable chunks.

Embedding Model: Each text chunk is transformed into a high-dimensional vector (embedding), capturing its semantic meaning.

Vector Database (Vector DB): These embeddings are stored in a dedicated database (e.g., Chroma, Pinecone) for efficient similarity search.

Retriever: When a user asks a question, the query is also converted into a vector. The retriever searches the Vector DB for the top k most similar document chunks.

LLM (Generator): The retrieved context chunks are combined with the original user query to create a single, augmented prompt. The LLM then generates the final, contextually accurate answer.






















# How to use this RAG AI Teaching assistant on your own data
## Step 1 - Collect your videos
Move all your video files to the videos folder

## Step 2 - Convert to mp3
Convert all the video files to mp3 by ruunning video_to_mp3

## Step 3 - Convert mp3 to json 
Convert all the mp3 files to json by ruunning mp3_to_json

## Step 4 - Convert the json files to Vectors
Use the file preprocess_json to convert the json files to a dataframe with Embeddings and save it as a joblib pickle

## Step 5 - Prompt generation and feeding to LLM

Read the joblib file and load it into the memory. Then create a relevant prompt as per the user query and feed it to the LLM



