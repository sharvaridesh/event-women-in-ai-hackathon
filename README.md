<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Professional Matchmaker: Job Matching with Resume Using Milvus and LangChain</title>
</head>
<body>
    <h1>Professional Matchmaker: Job Matching with Resume Using Milvus and LangChain</h1>

    <p><strong>Professional Matchmaker</strong> is a job matching system that leverages <strong>Milvus</strong>, an open-source vector database, and <strong>LangChain</strong>, a powerful library for creating LLM-powered pipelines, to match job postings with candidate resumes. By utilizing <strong>Sentence-Transformers</strong> for embedding generation and <strong>Milvus vector search</strong>, it retrieves the most relevant jobs from a dataset of job postings and generates an explanation for why each job is a good fit for the candidate.</p>

    <h2>Overview</h2>
    <p>The pipeline performs the following steps:</p>
    <ol>
        <li><strong>Embed Resume:</strong> A resume is input as text, and its embedding is generated using <strong>Sentence-Transformers</strong>.</li>
        <li><strong>Search Job Postings:</strong> The generated embedding is used to query the Milvus database, which stores job postings with embeddings.</li>
        <li><strong>Explain Job Fit:</strong> A <strong>LangChain</strong>-powered GPT model generates an explanation of why each job is a good fit based on the resume.</li>
    </ol>
    <p>The output is a list of jobs with explanations that match the user’s experience and qualifications.</p>

    <h2>Features</h2>
    <ul>
        <li><strong>Job Matching:</strong> Retrieves top job postings that are most relevant to the candidate's resume using cosine similarity.</li>
        <li><strong>Explanation Generation:</strong> Provides a human-readable explanation of why each job is suitable for the candidate using an LLM (e.g., GPT-4).</li>
        <li><strong>Sentence-Transformers:</strong> Leverages the <strong>Sentence-Transformers</strong> model for embedding generation, optimized for sentence-level similarity.</li>
    </ul>

    <h2>Requirements</h2>
    <p>1. <strong>Milvus</strong>: Set up and running to store job postings.</p>
    <p>2. <strong>Sentence-Transformers</strong>: Used for generating embeddings for resumes and job postings.</p>
    <p>3. <strong>LangChain</strong>: A Python framework to interact with LLMs like GPT-4.</p>
    <p>4. <strong>Python 3.7+</strong>: Ensure compatibility with libraries used in the project.</p>

    <h3>Install Dependencies</h3>
    <pre><code>pip install pymilvus sentence-transformers langchain</code></pre>

    <h2>Setup Instructions</h2>

    <h3>1. Set Up Milvus Database</h3>
    <p>Make sure Milvus is installed and running. You can follow the installation guide in the <a href="https://milvus.io/docs/install_standalone-docker.md" target="_blank">Milvus documentation</a> to get started.</p>
    <p>Ensure you have a collection named <code>job_postings_linkedin</code> in Milvus with job embeddings stored under the <code>embedding</code> field.</p>

    <h3>2. Generate Embeddings with Sentence-Transformers</h3>
    <p>You will use <strong>Sentence-Transformers</strong> to generate embeddings for both resumes and job postings. Ensure you have installed the package and chosen a suitable model for your needs (e.g., <code>all-MiniLM-L6-v2</code>).</p>
    <pre><code>from sentence_transformers import SentenceTransformer

def get_embedding_from_text(text):
    model = SentenceTransformer('all-MiniLM-L6-v2')
    return model.encode(text)</code></pre>

    <h3>3. Run the Pipeline</h3>
    <p>You can now run the script to interact with the system. When prompted, input your resume text as a string. The system will return the top 5 job postings with explanations for why they are a good fit for the candidate.</p>
    <p>Example usage:</p>
    <pre><code>Enter your resume text: "Experienced software engineer with expertise in Python, AI, and machine learning."</code></pre>

    <h2>Code Walkthrough</h2>

    <h3><code>get_embedding_from_text</code></h3>
    <p>This function generates a vector embedding from the resume text using <strong>Sentence-Transformers</strong>.</p>
    <pre><code>from sentence_transformers import SentenceTransformer

def get_embedding_from_text(text):
    model = SentenceTransformer('all-MiniLM-L6-v2')  # Using a pre-trained model from Sentence-Transformers
    return model.encode(text)</code></pre>

    <h3><code>search_jobs</code></h3>
    <p>Searches for the most relevant job postings in the Milvus database based on the resume embedding. It uses cosine similarity for the search.</p>
    <pre><code>def search_jobs(resume_text):
    query_embedding = get_embedding_from_text(resume_text)
    search_params = {"metric_type": "COSINE", "params": {"nprobe": 10}}

    results = milvus_client.search(
        collection_name="job_postings_linkedin",
        data=[query_embedding],
        anns_field="embedding",
        param=search_params,
        limit=5,
        output_fields=["job_id", "title", "location"]
    )
    
    return results[0]</code></pre>

    <h3><code>generate_job_explanations</code></h3>
    <p>Generates a natural language explanation for why a job is a good fit based on the candidate's resume using LangChain and GPT-4.</p>
    <pre><code>def generate_job_explanations(resume_text):
    jobs = search_jobs(resume_text)
    llm = ChatOpenAI(model="gpt-4", api_key="your-openai-api-key")
    prompt_template = PromptTemplate(
        input_variables=["resume", "title", "location"],
        template=(
            "Given the candidate's resume: {resume}, explain why the role {title} "
            "in {location} is a good fit for them."
        )
    )
    chain = LLMChain(llm=llm, prompt=prompt_template)

    for job in jobs:
        title = job.entity['title']
        location = job.entity['location']
        explanation = chain.run(resume=resume_text, title=title, location=location)
        print(f"Job ID: {job.entity['job_id']}, Title: {title}, Location: {location}")
        print(f"Explanation: {explanation}\n")</code></pre>

    <h2>Example Output</h2>
    <p>The output from running the pipeline will look like this:</p>
    <pre><code>Job ID: 12345, Title: Software Engineer, Location: New York
Explanation: Based on your experience in software development, particularly with Python and AI, the role of Software Engineer in New York is a great fit because it involves working on cutting-edge AI applications.</code></pre>

</body>
</html>