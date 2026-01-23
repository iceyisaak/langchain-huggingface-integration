# Langchain HuggingFace Integration

Repo: https://github.com/iceyisaak/langchain-huggingface-integration

---

This project demonstrates how to integrate **LangChain** with **Hugging Face** to build AI-powered applications. It covers using Hugging Face models for text generation, embeddings, and building chains using the LangChain framework.

## 🚀 Features

* **Hugging Face Inference API**: Connect to thousands of models hosted on Hugging Face Hub without local installation.
* **Local Pipelines**: Instructions for running models locally using `transformers`.
* **LangChain Integration**: Implementation of `HuggingFaceHub` and `HuggingFaceEmbeddings`.
* **Environment Management**: Secure handling of API tokens using `.env` files.

## 🛠️ Prerequisites

* Python 3.8+
* A [Hugging Face](https://huggingface.co/) account.
* A Hugging Face **User Access Token** (Read or Write permissions). You can get one [here](https://huggingface.co/settings/tokens).

## 📥 Installation

1. **Clone the repository:**
```bash
git clone https://github.com/iceyisaak/langchain-huggingface-integration.git
cd langchain-huggingface-integration

```


2. **Install required dependencies:**
```bash
pip install langchain langchain-community huggingface_hub python-dotenv transformers sentence-transformers

```



## 🔐 Configuration

Create a file named `.env` in the root directory of the project and add your Hugging Face API token:

```env
HUGGINGFACEHUB_API_TOKEN=your_token_here_abc123

```

*Note: Ensure `.env` is added to your `.gitignore` to prevent leaking your credentials.*

## 📖 Usage

1. **Launch the Notebook:**
```bash
jupyter notebook langchain-huggingface-integration.ipynb

```


2. **Key Code Snippet:**
The notebook demonstrates initializing the environment and the model as follows:
```python
import os
from dotenv import load_dotenv
from langchain_community.llms import HuggingFaceHub

# Load variables from .env
load_dotenv()

# Initialize Hugging Face LLM
llm = HuggingFaceHub(
    repo_id="google/flan-t5-large",
    model_kwargs={"temperature": 0.5, "max_length": 64}
)

prompt = "What are the benefits of using LangChain with Hugging Face?"
print(llm.invoke(prompt))

```



## 📂 Project Structure

* `langchain-huggingface-integration.ipynb`: The main Jupyter notebook containing the code and explanations.
* `.env`: (To be created) Stores your secret API tokens.
* `requirements.txt`: (Optional) List of dependencies for the project.

---