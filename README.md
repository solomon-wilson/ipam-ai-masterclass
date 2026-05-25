🚀 IPAM USL 3-Week Short Course: Advanced Artificial Intelligence

Welcome to the Advanced Artificial Intelligence Short Course for Year 3 and 4 students at the Faculty of Information Systems & Technology, IPAM University of Sierra Leone!

Facilitator: Solomon Wilson | Deputy HOD IT & Audit, Sierra Leone Public Transport Authority (SLPTA)

This repository contains all the materials, daily code notebooks, and project guidelines required for the 3-week intensive program. We are moving beyond basic chatbot interactions to build enterprise-grade Reasoning Engines and Autonomous AI Agents using zero-budget cloud tools.

📅 Course Details & Logistics

Duration: 15th June to 3rd July 2026 (3 Weeks)

Time: 10:00 AM to 1:00 PM

Venue: IPAM Tower Hill Campus

Eligibility: Open to Years 3 and 4 Students

Registration: Centre for Consultancy & Continuous Professional Development

Course Fee: Le1,000

📁 Repository Structure

📦 ipam-advanced-ai-course
 ┣ 📂 week-1-foundations
 ┃ ┗ 📜 Day1_to_Day5_Notebooks.ipynb
 ┣ 📂 week-2-vector-rag
 ┃ ┗ 📜 Day6_to_Day10_Notebooks.ipynb
 ┣ 📂 week-3-agents
 ┃ ┗ 📜 Day11_to_Day15_Notebooks.ipynb
 ┣ 📂 presentations
 ┃ ┗ 📜 IPAM_USL_Course_Slides.pptx
 ┗ 📜 README.md


🎯 3-Week Hands-On Curriculum

This course is strictly hands-on. Every concept is paired with Python implementation.

Week 1: LLM Foundations & Advanced Prompt Engineering (June 15 - 19)

Day 1: Introduction to the Modern AI Ecosystem & Environment Setup (Google Colab, API Keys).

Day 2: Interacting with LLMs via APIs (Google Gemini 1.5 Flash).

Day 3: Prompt Engineering Techniques (Few-Shot, Chain-of-Thought).

Day 4: LangChain Basics: Prompt Templates & Output Parsers.

Day 5: Structured Data Extraction using Pydantic (Schema Validation).

Week 2: Enterprise Memory & RAG Systems (June 22 - 26)

Day 1: Understanding Text Embeddings and High-Dimensional Vector Spaces.

Day 2: Introduction to Vector Databases (Local implementation with ChromaDB).

Day 3: Document Loaders & Text Splitters (Processing PDFs, CSVs, and SQL Logs).

Day 4: Building a basic Retrieval-Augmented Generation (RAG) Chain.

Day 5: Advanced RAG: Semantic routing and preventing AI hallucinations on private data.

Week 3: Autonomous AI Agents & Capstone Projects (June 29 - July 3)

Day 1: Introduction to ReAct Architecture (Reasoning + Acting).

Day 2: Tool Calling: Binding Python functions to LLMs.

Day 3: Building an Agent with LangChain to query external APIs and Databases.

Day 4: Capstone Project Development Workshop.

Day 5: Final Project Presentations & Course Conclusion.

🛠️ Pre-requisites & Setup

To ensure everyone can participate regardless of laptop specifications, we are using Google Colab. No local installations are required.

Step 1: Claim Your Free Gemini API Key

Go to Google AI Studio.

Sign in with your Google account.

Click "Create API Key" and copy the generated string. Do not share this key publicly.

Step 2: Securely Store Your API Key in Colab

We will use Colab's Secrets manager to keep your key safe:

Open a new Google Colab Notebook.

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
llm = ChatGoogleGenerativeAI(model="gemini-2.5-flash", temperature=0)

# Test the brain
response = llm.invoke("What is the capital of Sierra Leone?")
print(response.content)


🏢 Real-World Application: The Capstone Project

As IT and Information Systems graduates, your goal isn't just to write code—it's to solve business problems.

During the final week, students will simulate an environment similar to the Sierra Leone Public Transport Authority. You will build a consolidated AI tool that an internal auditor or IT supervisor could use to:

Instantly query thousands of pages of compliance regulations and HR policies (RAG).

Automatically flag anomalies in server log data and financial records (Prompt Templates).

Execute API calls to check the live status of transit routes and generate automated audit reports (Tool Calling Agents).

📚 Resources & Documentation

Langchain Python Documentation

Google Gemini API Docs

ChromaDB Documentation

Created for the students of IPAM USL. Empowering the next generation of Sierra Leone's IT leaders.
