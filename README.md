# **Tools and Agents: Retriever, Embeddings, VectorStores, and LLM Integration**

This repository provides a step-by-step guide to set up **Tools and Agents** using LangChain and related libraries manually, including creating APIs for integrating the tools and agents.

## Setup Instructions

Follow these steps to set up your environment and run the project.

### Step 1: Download the Files

1. Download the provided files:  
   - `tools-and-agents.ipynb`  
   - `requirements.txt`  
   - `.env`

2. Place all files in a single folder on your machine. For example:  
   ```
   tools-and-agents/
   ├── tools-and-agents.ipynb
   ├── requirements.txt
   ├── .env
   ```

### Step 2: Create a Virtual Environment

1. Open a terminal in the folder where the files are located.  
2. Create a virtual environment by running the following command:  

   ```bash
   python -m venv venv
   ```  

3. Activate the virtual environment:  
   - On **Windows**:  
     ```bash
     venv\Scripts\activate
     ```  
   - On **macOS/Linux**:  
     ```bash
     source venv/bin/activate
     ```  

### Step 3: Install Dependencies

1. Ensure `pip` is updated:  
   ```bash
   pip install --upgrade pip
   ```  
2. Install the required libraries:  
   ```bash
   pip install -r requirements.txt
   ```  

### Step 4: Set Up the Environment Variables

1. Open the `.env` file using any text editor.  
2. Add your API keys and tokens in the following format:  

   ```
   GROQ_API_KEY=your_groq_api_key
   HF_TOKEN=your_huggingface_token
   ```  

   Save the file after editing.

### Step 5: Run the Jupyter Notebook

1. Install Jupyter Notebook if you don’t have it already:  
   ```bash
   pip install notebook
   ```  
2. Launch the notebook:  
   ```bash
   jupyter notebook
   ```  
3. Open `tools-and-agents.ipynb` in the Jupyter Notebook interface.  
4. Run each code cell sequentially to test and implement the functionality.

---

## Creating APIs

To create an API for the tools and agents, you can use **Flask** or **FastAPI** to expose your LangChain components over HTTP. Here’s a simple example using **Flask**:

### Step 1: Install Flask

If you don’t have Flask installed, add it to your `requirements.txt` file and install it:

```bash
pip install flask
```

### Step 2: Create a Simple Flask API

In your project folder, create a new Python file, e.g., `app.py`, and include the following code:

```python
from flask import Flask, request, jsonify
from langchain.agents import AgentExecutor
from langchain.tools import Tool

# Initialize Flask app
app = Flask(__name__)

# Initialize your tools (retriever, chat, etc.)
tools = [wiki, arxiv, retriever_tool]  # Add more tools if needed
agent_executor = AgentExecutor(agent=agent, tools=tools, verbose=True)

@app.route('/invoke', methods=['POST'])
def invoke_agent():
    # Get the query from the request body
    user_input = request.json.get('input', '')

    # Invoke the agent with the user input
    response = agent_executor.invoke({"input": user_input})

    # Return the response as JSON
    return jsonify({'response': response})

if __name__ == '__main__':
    app.run(debug=True)
```

### Step 3: Run the Flask API

1. Ensure your virtual environment is active.
2. Run the Flask app:

   ```bash
   python app.py
   ```

   This will start a local server at `http://127.0.0.1:5000/`.

### Step 4: Test the API

You can use **Postman** or **cURL** to test the API. For example, to invoke the agent:

```bash
curl -X POST -H "Content-Type: application/json" \
    -d '{"input": "What is the attention mechanism?"}' \
    http://127.0.0.1:5000/invoke
```

You should get a response like:

```json
{
  "response": "The attention mechanism is a technique used in deep learning models to focus on different parts of the input sequence when making predictions."
}
```

---

## Requirements

Make sure the `requirements.txt` file includes all necessary dependencies. The basic structure might look like:

```
langchain
python-dotenv
faiss-cpu
bs4
arxiv
jupyter
flask
```

---

## FAQs

1. **Why create a virtual environment?**  
   A virtual environment isolates project dependencies to avoid conflicts with global Python packages.

2. **What API keys are required?**  
   - **GROQ_API_KEY**: For the Groq model.  
   - **HF_TOKEN**: For HuggingFace embeddings.

3. **How to add more tools?**  
   Extend the `tools` list in the notebook by creating new retrievers, LLM tools, or document loaders.

4. **How do I create APIs for my tools?**  
   You can use Flask or FastAPI to expose your LangChain tools and agents as APIs. Refer to the example above for a simple Flask API setup.

---

## Connect with Me

Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/nahid-kawsar/)!  
