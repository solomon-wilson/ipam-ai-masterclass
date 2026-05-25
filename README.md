🚀 IPAM USL AI Masterclass: Fundamentals for the Data Domain

Welcome to the AI Masterclass for Final-Year Information Systems & Technology Students at IPAM University of Sierra Leone!

Facilitator: Solomon Wilson

This repository contains all the materials, presentation slides, and hands-on code required to build enterprise-grade AI applications with zero budget. We are moving beyond simple chatbots to build Reasoning Engines that can query public transport schedules, analyze audit logs, and automate compliance tasks.

📁 Repository Structure

📦 ipam-ai-masterclass
 ┣ 📂 presentations
 ┃ ┗ 📜 IPAM_USL_AI_Masterclass.pptx    # Downloadable slide deck
 ┣ 📂 notebooks
 ┃ ┗ 📜 AI_Masterclass_HandsOn.ipynb    # Main Google Colab Notebook
 ┗ 📜 README.md                         # You are here!


(Note for Instructor: Upload the .pptx exported from our previous step into the presentations folder, and upload your Python code as a Jupyter Notebook in the notebooks folder).

🎯 What You Will Learn

In this 2-hour hands-on session, you will learn how to:

Connect to LLMs: Interact with Google's Gemini 1.5 Flash via API.

Prompt Engineering: Use Langchain chains to structure predictable outputs.

RAG (Retrieval-Augmented Generation): Ground the AI in private enterprise data (e.g., SLPTA Transport Policies) using Vector Databases (ChromaDB) to eliminate hallucinations.

AI Agents (ReAct): Build autonomous agents that can trigger Python tools to fetch real-time route statuses or SQL audit logs.

🛠️ Pre-requisites & Setup

To ensure everyone can participate regardless of hardware limits, we are using Google Colab. No local installations are required.

Step 1: Claim Your Free Gemini API Key

Go to Google AI Studio.

Sign in with your Google account.

Click "Create API Key" and copy the generated string. Do not share this key publicly.

Step 2: Open the Notebook

Navigate to the notebooks/ folder in this repository.

Click on the AI_Masterclass_HandsOn.ipynb file.

Click the "Open in Colab" badge at the top of the file (or download it and upload it to colab.research.google.com).

Step 3: Securely Store Your API Key in Colab

We will use Colab's Secrets manager to keep your key safe:

Open your Colab Notebook.

On the left-hand sidebar, click the 🔑 Key Icon (Secrets).

Click Add new secret.

Set the Name to GEMINI_API_KEY.

Paste your copied API key into the Value field.

Toggle the switch to grant the notebook access to the secret.

💻 Quick Start: Running the Code

Once your environment is set up, run the first cell in your notebook to install the required dependencies:

!pip install -q google-generativeai langchain langchain-google-genai chromadb pydantic


Then, initialize your connection to the AI Brain:

import os
from google.colab import userdata
import google.generativeai as genai
from langchain_google_genai import ChatGoogleGenerativeAI

# Fetch the key securely
os.environ["GOOGLE_API_KEY"] = userdata.get('GEMINI_API_KEY')
genai.configure(api_key=os.environ["GOOGLE_API_KEY"])

# Initialize the Gemini LLM
llm = ChatGoogleGenerativeAI(model="gemini-1.5-flash", temperature=0)

# Test the brain
response = llm.invoke("What is the capital of Sierra Leone?")
print(response.content)


(Follow the rest of the exercises sequentially in the notebook!)

🏢 Real-World Application: The SLPTA Use Case

As IT and Information Systems graduates, your goal isn't just to write code—it's to solve business problems.

In this workshop, we simulate an environment similar to the Sierra Leone Public Transport Authority. You will build tools that an internal auditor or IT supervisor could use to:

Instantly query thousands of pages of compliance regulations (RAG).

Automatically flag anomalies in 50GB of server log data (Prompt Templates).

Execute API calls to check the live status of transit routes (Tool Calling Agents).

📚 Resources & Documentation

Langchain Python Documentation

Google Gemini API Docs

ChromaDB Documentation

Created for the students of IPAM USL. Empowering the next generation of Sierra Leone's IT leaders.
