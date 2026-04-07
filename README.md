## 📖 Project Description

This project presents a Retrieval-Augmented Generation (RAG) based chatbot developed using Flowise, designed to deliver accurate and context-aware responses from custom documents. Unlike traditional chatbots that rely solely on pre-trained knowledge, this system enhances response quality by retrieving relevant information from a user-provided dataset before generating answers. This ensures that outputs are grounded in factual content and reduces the chances of hallucination.

The chatbot workflow begins with document ingestion through a file loader, which supports formats such as PDF and JSON. The loaded content is then processed using a Recursive Character Text Splitter, which breaks large documents into smaller, manageable chunks. This step is essential for improving retrieval accuracy and ensuring that the language model can efficiently process the data.

Next, the system leverages Google Gemini Embeddings to convert each text chunk into vector representations. These embeddings capture the semantic meaning of the text, allowing for similarity-based search. The vectors are stored in an in-memory vector database, enabling fast and efficient retrieval of relevant information based on user queries.

When a user asks a question, the system retrieves the most relevant chunks from the vector store and passes them to the Mistral AI language model. The Conversational Retrieval QA Chain ensures that responses are generated using both the retrieved context and the ongoing chat history, enabling a more natural and coherent conversation. Additionally, buffer memory is used to maintain context across multiple interactions, making the chatbot capable of handling follow-up questions effectively.

Overall, this project demonstrates how combining retrieval mechanisms with generative AI can significantly improve the reliability, transparency, and usefulness of conversational systems. It is particularly well-suited for applications such as document-based question answering, research assistance, and knowledge management systems.
