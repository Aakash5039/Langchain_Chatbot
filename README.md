
### Description

This project builds a smart conversational AI using LangChain and Cohere Chat Model. It reads documents, breaks them into manageable pieces, and creates text embeddings for efficient processing. The AI can remember the context of previous interactions, making conversations feel natural and coherent. By using advanced language models, the system provides accurate and relevant responses, making it suitable for various applications in natural language understanding.


The documents are stored as a .txt files. There are two folders made, one focusing on research papers, and the other contining lecture notes from the following lectures
Lecture Link: https://stanford-cs324.github.io/winter2022/lectures/

The code loads text documents from a specified directory using `DirectoryLoader` and stores them in a list. It then splits these documents into smaller chunks of 400 characters with a 30-character overlap using `RecursiveCharacterTextSplitter`. The chunks are converted into embeddings with the `HuggingFaceEmbeddings` model, capturing their semantic meaning. These embeddings are stored in a `Chroma` vector store, which is created from the chunked documents and saved in a database. Finally, a retriever is set up to search for the top 7 similar embeddings in the `Chroma` database, facilitating quick and accurate information retrieval based on semantic similarity.

The model uses the Cohere chat model and Hugging Face embeddings to convert queries into vectors. A retriever searches for similar vectors in the vector store, and contextual compression filters out less relevant features. The filtered chunks, along with the user query and chat history, are then passed to the Cohere chat model. Using this information, the model generates a response.


Future Improvemets:
1) Implementing Routing for effective and accurate data retreival
2) Deploying the model on streamlit
3) Try to implement automatic chat saving and retreival.
