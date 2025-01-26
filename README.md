# Professional Matchmaker: Job Matching with Resume Using Milvus and LangChain

**Professional Matchmaker** is a job matching system that leverages **Milvus**, an open-source vector database, and **LangChain**, a powerful library for creating LLM-powered pipelines, to match job postings with candidate resumes. By utilizing **Sentence-Transformers** for embedding generation and **Milvus vector search**, it retrieves the most relevant jobs from a dataset of job postings and generates an explanation for why each job is a good fit for the candidate.

## Overview

The pipeline performs the following steps:

1. **Embed Resume**: A resume is input as text, and its embedding is generated using **Sentence-Transformers**.
2. **Search Job Postings**: The generated embedding is used to query the Milvus database, which stores job postings with embeddings.
3. **Explain Job Fit**: A **LangChain**-powered GPT model generates an explanation of why each job is a good fit based on the resume.

The output is a list of jobs with explanations that match the user’s experience and qualifications.

## Features

- **Job Matching**: Retrieves top job postings that are most relevant to the candidate's resume using cosine similarity.
- **Explanation Generation**: Provides a human-readable explanation of why each job is suitable for the candidate using an LLM (e.g., GPT-4).
- **Sentence-Transformers**: Leverages the **Sentence-Transformers** model for embedding generation, optimized for sentence-level similarity.

## Requirements

1. **Milvus**: Set up and running to store job postings.
2. **Sentence-Transformers**: Used for generating embeddings for resumes and job postings.
3. **LangChain**: A Python framework to interact with LLMs like GPT-4.
4. **Python 3.7+**: Ensure compatibility with libraries used in the project.

### Install Dependencies

```bash
pip install pymilvus sentence-transformers langchain
