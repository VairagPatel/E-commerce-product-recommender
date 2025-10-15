E-commerce Product Recommendation System with Gen AI
This project delivers an advanced, end-to-end product recommendation system powered by Retrieval-Augmented Generation (RAG) and the Google Gemini API. It fundamentally shifts away from traditional collaborative filtering by focusing on semantic understanding of user needs, enabling the system to interpret complex, natural language queries and provide personalized, highly relevant product suggestions.

🌟 Features
RAG-Powered Semantic Search: The core engine uses RAG techniques to interpret detailed, free-form user intent ("I need a durable, lightweight drone for travel") rather than being limited to fixed categories or brands.

Dynamic Personalization: Users can input preferences like department, category, brand, and maximum price range, which are semantically processed to generate tailored recommendations.

Interactive UI: Built with Streamlit for an intuitive and user-friendly web interface.

Efficient Data Pipeline: The system preprocesses, tokenizes, and saves the vector store to disk for persistent storage, eliminating redundant processing and reducing API call costs after the initial setup.

Comprehensive Data Analysis: Includes initial visualizations like price distribution across top categories and discount percentage distribution.

💻 Technical Stack
Component	Technology	Purpose
Generative AI	Google Gemini API	Provides high-quality embeddings and natural language generation (LLM) for explanations.
RAG Orchestration	Langchain	Manages the retrieval (vector store) and generation (Gemini) flow.
Frontend/UI	Streamlit	Interactive dashboard for user input and results display.
Vector Store	FAISS	Efficient storage and retrieval of product embeddings.
Data Science	Pandas, Seaborn, Matplotlib	Data manipulation, analysis, and visualization.

Export to Sheets
⚙️ Installation and Setup
Follow these steps to get the project running on your local machine.

1. Clone the Repository
Bash

git clone https://github.com/your-username/ecommerce-product-recommendation.git
cd ecommerce-product-recommendation
2. Set Up Python Environment
It is highly recommended to use a virtual environment (venv).

Bash

# Create and activate the virtual environment (Example for Linux/macOS)
python -m venv venv
source venv/bin/activate
# For Windows: .\venv\Scripts\activate
3. Install Dependencies
The dependencies file is configured for Gemini/Google GenAI integration.

Bash

# This installs all required libraries, including langchain-google-genai, pandas, and streamlit
pip install -r requirements.txt
4. Configure Gemini API Key
You must secure your API key in an environment file.

Create a file named .env in the project root directory.

Add your Gemini API key to the file in the following format:

GEMINI_API_KEY=your-api-key
▶️ Usage
1. Prepare Data and Paths
Place your e-commerce dataset (e.g., flipkart_com_ecommerce_sample.csv) in the project root.

Ensure the dataset_path variable in your app.py file points to the correct CSV name.

2. Run the Streamlit Application
Execute the main application file from your active terminal:

Bash

streamlit run app.py
3. Generate the Vector Database Index (One-Time Setup)
The RAG index (vectorstore/index.faiss) is not included in the repository and must be generated on the first run.

Access the application URL provided by Streamlit.

Navigate to the Product Recommendation feature.

Input your first query.

The system will begin the one-time, memory-intensive process of generating vector embeddings for all products and saving them to disk. Wait for this process to complete.

Once the file is generated, all future recommendations will be fast, relying on the stored index.

📂 Project Structure
ecommerce-product-recommendation/
├── venv/
├── .env
├── app.py                      # Main Streamlit application and UI
├── data_processing.py          # Data cleaning, analysis, and embedding/vector store logic
├── recommendation_utils.py     # Implements the LangChain RAG pipeline and Gemini calls
├── requirements.txt            # Project dependencies
└── README.md
💡 Future Enhancements
The following features are planned for future development to enhance accuracy and robustness:

User Authentication & Profiles: Implement user profiles to track long-term behavior.

Behavioral Data Integration: Expand the system to include explicit user reviews and ratings alongside semantic search.

Scalability Optimization: Optimize the data processing and vector retrieval pipeline to handle large-scale, production-level datasets.

Advanced AI Models: Explore state-of-the-art NLP and deep learning models for even greater accuracy.

🤝 Contributing
Contributions are welcome! Feel free to open an issue or submit a pull request if you have ideas, suggestions, or bug reports. Please adhere to the project's code of conduct.

📄 License
This project is licensed under the MIT License.
