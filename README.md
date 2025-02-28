# PDF Chatbot

This project demonstrates a simple chatbot that answers questions based on information extracted from uploaded PDF documents. It leverages Retrieval Augmented Generation (RAG) using LangChain, ChromaDB, and a pre-trained language model.

## Features

* **Upload PDFs:** Allows users to upload multiple PDF files (up to 5) for analysis.
* **Text Extraction:** Extracts text content from the uploaded PDFs and stores it for processing.
* **Chunking:** Splits the extracted text into smaller chunks for efficient embedding and retrieval.
* **Embeddings:** Generates embeddings for each text chunk using a pre-trained Sentence Transformer model (`all-MiniLM-L6-v2`).
* **Vector Database:** Stores the embeddings and text chunks in a ChromaDB collection for fast similarity search.
* **Question Answering:** Enables users to ask questions about the PDF content through a conversational interface.
* **Retrieval:** Retrieves the most relevant text chunks based on the user's query using similarity search.
* **Answer Generation:** Generates an answer using a pre-trained language model (`google/flan-t5-small`) based on the retrieved context and the user's query.


## How it Works

1. **PDF Upload and Processing:** Users upload PDF files, and the code extracts the text content from them.
2. **Chunking:** The extracted text is divided into smaller chunks to preserve context and improve retrieval efficiency.
3. **Embeddings:** Embeddings are generated for each chunk using a pre-trained Sentence Transformer model, converting text into numerical representations.
4. **Vector Database:** The embeddings and text chunks are stored in a ChromaDB collection, allowing for fast similarity search.
5. **Query Processing:** When a user asks a question, an embedding is generated for the query.
6. **Retrieval:** The vector database is queried to find the most similar text chunks to the query embedding.
7. **Answer Generation:** The retrieved chunks and the user's query are fed into a pre-trained language model, which generates an answer based on the provided context.

## Getting Started

### Prerequisites

* Python 3.8 or higher
* Required libraries (install using `pip`):
### Usage

1. **Run the Code:** Execute the Python script in a Google Colab environment.
2. **Upload PDFs:** Use the Gradio interface to upload your PDF files.
3. **Ask Questions:** Enter your questions in the chatbot interface and get answers based on the PDF content.


## Limitations

* The accuracy and relevance of the answers depend on the quality of the PDF content and the performance of the pre-trained models used ( which in our case, the accuracy is low) {The generation Evaluation metrics: Average BLEU Score: 0.298 Average ROUGE- L F1 Score: 0.604}.
* The "google/flan-t5-small" model we used is a relatively lightweight model. Larger and more sophisticated language models might generate text that is closer to the reference answers in terms of phrasing and word order, leading to higher BLEU scores.
* Error handling and input validation could be further improved for robustness.
* The sample generated and reference answers you provided are only two examples. Evaluating on a larger and more diverse dataset would give you a more comprehensive understanding of the model's performance.

## Contributing

Feel free to contribute to this project by opening issues or submitting pull requests. Your feedback and suggestions are always welcome!

## License

This project is licensed under the [MIT License](LICENSE).
