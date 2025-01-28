# **Tools and Agents Setup Guide**

This guide will walk you through the process of setting up the **Tools and Agents** notebook environment, which includes creating a virtual environment, copying the code from the provided `tools_and_agents.ipynb` file, and setting up the required files. Additionally, it includes instructions for installing dependencies and configuring your environment.

## **Table of Contents**

1. [Setting Up the Virtual Environment](#setting-up-the-virtual-environment)
2. [Copying the Code from the Notebook](#copying-the-code-from-the-notebook)
3. [Required Files](#required-files)
4. [Installation of Dependencies](#installation-of-dependencies)
5. [Running the Code](#running-the-code)
6. [Contact Information](#contact-information)

---

## **Setting Up the Virtual Environment**

Before you start, it's essential to create a virtual environment to ensure that dependencies do not interfere with other projects.

1. **Create a Virtual Environment:**

   - For **Windows**:
     ```bash
     python -m venv venv
     ```
   
   - For **macOS/Linux**:
     ```bash
     python3 -m venv venv
     ```

2. **Activate the Virtual Environment:**

   - For **Windows**:
     ```bash
     venv\Scripts\activate
     ```
   
   - For **macOS/Linux**:
     ```bash
     source venv/bin/activate
     ```

---

## **Copying the Code from the Notebook**

1. Download the `tools_and_agents.ipynb` file provided.
   
2. Open the file using **Jupyter Notebook** or **JupyterLab** and review the code provided. The file contains all the necessary code for setting up tools, agents, document loaders, embeddings, vector stores, and retrievers.

3. Copy the code blocks as described and paste them into your working Python scripts. The notebook should guide you step-by-step for each tool and agent setup.

---

## **Required Files**

Make sure you have the following files in your project directory:

1. **`requirements.txt`**: This file contains all the necessary libraries that need to be installed. Below is a sample `requirements.txt` file:

   ```txt
   langchain
   langchain_community
   langchain_huggingface
   langchain_groq
   langchain_core
   python-dotenv
   fastapi
   uvicorn
   faiss-cpu
   chromadb
   arxiv
   beautifulsoup4
   ```

2. **`.env` File**: The `.env` file contains your API keys and other environment variables. Add the following to the `.env` file:

   ```txt
   HF_TOKEN=your_huggingface_api_token
   GROQ_API_KEY=your_groq_api_key
   ```

---

## **Obtaining API Keys**

You need to create API keys for **Hugging Face** and **Groq** to access the respective services.

### **1. Hugging Face API Key**

To obtain your Hugging Face API key, follow these steps:

1. Go to [Hugging Face's website](https://huggingface.co/).
2. Create an account or log in to your existing account.
3. Once logged in, go to your account settings by clicking on your profile picture in the top-right corner and selecting "Settings."
4. On the left menu, select the "Access Tokens" section.
5. Click the "New Token" button to generate a new API key.
6. Copy the generated token and paste it into your `.env` file as `HF_TOKEN`.

### **2. Groq API Key**

To obtain your Groq API key, follow these steps:

1. Go to [Groq's website](https://groq.com/).
2. Create an account or log in to your existing account.
3. Navigate to the **API** section of your account dashboard.
4. Request access to the API key if you haven't already done so.
5. Once granted access, copy the API key and paste it into your `.env` file as `GROQ_API_KEY`.

---

## **Installation of Dependencies**

To install all the required dependencies:

1. Make sure your virtual environment is activated (see above).
2. Install the required packages from `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

---


## **Contact Information**

If you have any questions or need further assistance, feel free to reach out to me:

- **LinkedIn**: [Nahid Kawswr](https://www.linkedin.com/in/nahidkawswr/)
