# Document Query Chatbot

A Streamlit-based chatbot that processes text files, clusters sentences by topic using K-means, and answers queries with relevant sentences using the `all-MiniLM-L6-v2` sentence transformer model. Built in Google Colab with ngrok for public access, this project showcases NLP, topic clustering, and web app development.

![Demo](Demo/Capture_1.png)

## Features
- **File Upload**: Upload `.txt` files (100–1000 words) with single or multiple topics.
- **Query Processing**: Enter queries (e.g., "How is AI used in healthcare?") with abbreviation support (e.g., "AI" → "artificial intelligence").
- **Topic Clustering**: Groups sentences into topics (2–5 clusters) using K-means on sentence embeddings.
- **Top-K Results**: Returns 1–5 most relevant sentences with similarity scores and explanations.
- **Robustness**: Handles edge cases (empty files, vague queries) with clear error messages.
- **Web Interface**: Streamlit UI with file uploader, query input, and sliders for customization.

## Tech Stack
- **Python**: Core programming language.
- **Streamlit**: Web app framework for the UI.
- **sentence-transformers**: `all-MiniLM-L6-v2` for sentence embeddings.
- **scikit-learn**: K-means clustering for topic grouping.
- **NLTK**: Text tokenization and query preprocessing (lemmatization).
- **PyTorch**: Backend for model computations.
- **ngrok**: Public URL tunneling for Colab.
- **Google Colab**: Development and testing environment.

## Setup (Google Colab)
1. **Open the Notebook**:
   - Download `document_query_chatbot.ipynb` from this repository.
   - Upload to [Google Colab]([https://colab.research.google.com/](https://colab.research.google.com/drive/1ezjQAFxC1TMxKuiWbhXiSGsRPgr22-gA?usp=sharing)).
   - Use Python 3 runtime (GPU optional for faster processing).
2. **Prepare Text Files**:
   - Place `sample.txt`, `sample2.txt`, `mixed_sample.txt`, and `complex_sample.txt` in `/content/drive/MyDrive/`.
   - Alternatively, upload files via Colab’s sidebar (`folder icon > Upload`).
3. **Run Cells Sequentially**:
   - **Cell 1**: Installs libraries and ngrok.
   - **Cell 2**: Mounts Google Drive and downloads NLTK resources.
   - **Cell 3**: Configures ngrok with an authtoken.
   - **Cell 4**: Saves the Streamlit app (`app.py`).
   - **Cell 5**: Runs the app and provides a public ngrok URL.
   - **Cell 6**: Fallback for testing without Streamlit/ngrok.
4. **Access the App**:
   - Click the ngrok URL from Cell 5 (e.g., `https://abc123.ngrok.io`).
   - Upload a text file, enter a query, set clusters/top-k, and view results.

## Usage
1. **Upload a File**:
   - Use `complex_sample.txt` (~800 words, covers AI, renewable energy, quantum computing, biotech).
2. **Enter a Query**:
   - Examples: "How is AI used in healthcare?", "What’s RE’s role in climate change?", "How does quantum computing help AI?".
3. **Set Parameters**:
   - Number of clusters (2–5): Try 4 for multi-topic files.
   - Number of sentences (1–5): Try 3 for detailed results.
4. **View Results**:
   - **Top Matching Sentences**: Relevant sentences with topics, scores, and explanations.
   - **Expander**: All sentences with their clusters and scores.
5. **Test Edge Cases**:
   - Empty query: Should show "Error: Please enter a query!".
   - Single-sentence file: Should show "Error: File must contain at least two sentences.".

## Sample Files
- **`sample.txt`**: AI-focused (~100 words).
- **`sample2.txt`**: Renewable energy (~100 words).
- **`mixed_sample.txt`**: AI and renewable energy (~200 words).
- **`complex_sample.txt`**: AI, renewable energy, quantum computing, biotechnology (~800 words).

## Demo
- **Colab Demo**: Run `document_query_chatbot.ipynb` in Colab to test with ngrok.
- **Live Demo** (Planned): Deployed on Streamlit Community Cloud (link TBD).

## Installation (Local Setup, Optional)
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/document-query-chatbot.git
   cd document-query-chatbot
