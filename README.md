# RAG_Chatbot
----------------

## requirements : pip install -r requirements.txt

Step-by-Step Process
1. Import Required Libraries
Streamlit (st) for UI
LangChain modules for document retrieval, embeddings, and LLM chat
Logging and warnings are disabled for cleaner output
2. Setup Streamlit UI
Displays a title: "Chat with me!"
Maintains chat history using st.session_state.messages
Displays past messages in chat format
3. Load and Embed PDF Data
Uses PyPDFLoader to load the document (attenstion_is_all_you_need.pdf)
Splits the document into smaller chunks using RecursiveCharacterTextSplitter
Creates a vector database using VectorstoreIndexCreator with HuggingFaceEmbeddings
4. Retrieve User Input
st.chat_input() collects user questions
The question is displayed in the chat and stored in st.session_state.messages
5. Define Groq Chat Model
Uses ChatGroq with llama3-8b-8192
Constructs a system prompt (ChatPromptTemplate) to ensure precise responses
6. Query the Vector Store
Retrieves relevant chunks from the PDF using the vector store
Uses RetrievalQA to pass the retrieved data to Groq’s LLM
Extracts and returns the final response
7. Display Assistant Response
Outputs the response in chat
Stores the assistant’s response in st.session_state.messages
8. Error Handling
Catches and displays errors if something goes wrong during execution

## to run app : streanlit run app.py
