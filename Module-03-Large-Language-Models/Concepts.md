# 📘 Week 3 – Session 1  
## Module 3 – Intelligent API Systems & LLM Applications

This session explored advanced techniques for working with modern AI APIs. We studied how Large Language Models (LLMs) operate, how embeddings and vector databases power semantic search, how Retrieval-Augmented Generation (RAG) improves accuracy, and how structured prompts, schemas, and evaluation methods help build reliable AI-driven applications.

The emphasis was on designing scalable, efficient, and production-ready AI systems.

---

#  1. Module 3 Overview

Module 3 is centered around:

- Communicating with advanced AI APIs
- Generating and analyzing text using LLMs
- Structuring and extracting data
- Building retrieval-based AI systems
- Creating intelligent applications

The objective is to move beyond basic prompting and develop structured AI workflows.

---

#  2. API Access & Key Management

To use AI services, authentication through an API key is required.

Key reminders:

- Generate API key from aipipe.org
- Store keys securely
- Avoid exposing keys in public repositories
- Use environment variables for safety

Frequent errors:

- Hardcoding API credentials
- Incorrect proxy configuration
- Ignoring usage limits

Proper key handling is essential for secure development.

---

#  3. Working Principle of LLMs

Large Language Models:

- Are not conscious systems
- Do not think like humans
- Operate using probability predictions

They are built using:

- Transformer-based neural networks
- Large-scale training datasets
- Deep learning algorithms

Their core function is predicting the next most probable token.

---

#  4. Tokens and Cost Calculation

Text input is broken into tokens.

Important facts:

- Tokens are smaller than words
- Usage cost depends on token count
- Both input and output tokens are billed

Efficient prompt design helps reduce unnecessary token usage and cost.

---

#  5. Role of Self-Attention

Self-attention allows models to:

- Capture word relationships
- Understand contextual meaning
- Focus on important parts of input

It helps the model link distant words within a sentence.

---

#  6. Context Window Constraints

LLMs have a limited context window.

Implications:

- Cannot process unlimited text
- Long conversations may lose earlier details
- Truncation may occur

External knowledge retrieval systems are used to overcome this limitation.

---

#  7. Understanding Embeddings

Embeddings transform:

- Text
- Images
- Audio

into numerical vector representations.

Why embeddings matter:

- Measure similarity
- Enable semantic search
- Cluster related information

Multimodal embeddings allow comparison across different data types.

---

#  8. Semantic Topic Grouping

Using embeddings, systems can:

- Identify similar documents
- Automatically group topics
- Detect thematic patterns

This method understands meaning rather than relying only on keywords.

---

#  9. Vector Storage Systems

Vector databases are designed to store embeddings.

They provide:

- Fast similarity lookup
- Efficient nearest-neighbor search
- High-speed retrieval

Applications include:

- Smart search engines
- Recommendation systems
- RAG-based solutions

---

#  10. Retrieval-Augmented Generation (RAG)

RAG enhances response quality by:

1. Searching relevant documents
2. Supplying them to the LLM
3. Generating informed answers

Advantages:

- Minimizes hallucinations
- Improves factual accuracy
- Uses external knowledge

RAG connects models to real data.

---

#  11. Hybrid Retrieval Models

Hybrid systems combine:

- Traditional keyword search
- Semantic vector search

Benefits:

- Exact match precision
- Contextual understanding
- Balanced relevance

This approach strengthens search reliability.

---

#  12. Base64 Data Encoding

Binary content cannot be directly sent to text-based models.

Base64 encoding converts:

- Images
- Audio
- Files

into text format for transmission.

It ensures compatibility with API systems.

---

#  13. Vision-Capable Models

Modern AI models can process visual data.

Capabilities include:

- Image recognition
- Text extraction (OCR)
- Object detection
- Frame-by-frame video analysis

Use cases:

- Surveillance monitoring
- Safety inspection
- Online exam supervision
- Automated visual review systems

Vision extends AI beyond text interaction.

---

#  14. Designing Effective Prompts

Prompt structure significantly impacts output quality.

Best practices:

- Clearly define instructions
- Specify output format (JSON/XML)
- Provide examples
- Test and refine prompts
- Document prompt results

Well-designed prompts reduce ambiguity and improve reliability.

---

#  15. Emotion & Sentiment Detection

LLMs can determine tone such as:

- Positive
- Negative
- Neutral

Applications include:

- Financial trend analysis
- Political campaign monitoring
- Brand reputation tracking
- Social media insights

Sentiment analysis enables large-scale text evaluation.

---

#  16. Structured Data Extraction

LLMs can convert messy text into organized JSON.

Example:

Input:
"Rohan ordered 4 pizzas costing 800 rupees."

Output:
{
  "customer": "Rohan",
  "quantity": 4,
  "amount": 800
}

This supports automation and database integration.

---

#  17. Using Schemas for Control

Schemas define expected output structure.

Advantages:

- Standardized responses
- Easy integration with applications
- Reduced format errors
- Improved consistency

Schemas make AI outputs predictable.

---

#  18. Integrating Function Calls

LLMs can trigger predefined functions.

Example:

User: "Reserve a hotel room"
Model → Calls booking function

This enables:

- Task automation
- Real-time execution
- Smart digital assistants

Function calling transforms chatbots into actionable systems.

---

#  19. AI Agents & Tool Usage

Agents are systems that:

- Select tools automatically
- Execute multiple steps
- Combine different APIs
- Perform complex workflows

Agents create intelligent, autonomous AI applications.

---

#  20. Evaluating LLM Performance

Proper testing ensures:

- Accurate outputs
- Controlled costs
- Fast response time
- System stability

Evaluation methods include:

- Structured prompt testing
- YAML-based configuration
- Output assertions
- Model comparison
- Regression testing

Continuous evaluation improves system reliability.

---

##  Week 3 – Session 1 Completed 🎉

# 📘 Week 3 – Session 2  
## Module 3 – Practical Embeddings, Multimodal AI & RAG Systems

This session focused on building intelligent retrieval systems using embeddings and vector search. The goal was to understand how semantic similarity works in real applications and how Retrieval-Augmented Generation (RAG) improves answer quality.

The session emphasized implementation over theory.

---

#  1. Session Focus

Main topics covered:

- Text embeddings
- Multimodal embeddings
- Cosine similarity
- Vector storage
- Document chunking
- RAG pipeline design
- Deployment troubleshooting

These concepts are central to Project 1.

---

#  2. What Are Embeddings?

Embeddings transform text into numeric vectors.

Key ideas:

- Each sentence becomes a point in multi-dimensional space
- Similar meanings → closer vectors
- Used for semantic comparison

Embeddings are:

- Faster than chat models
- Lower cost for similarity tasks

---

#  3. Generating Embeddings

Two approaches were demonstrated:

1. Local embedding models (Sentence Transformers)
2. API-based embedding models (e.g., `text-embedding-3-small`)

Both produce fixed-length vectors usable for similarity search.

---

#  4. Measuring Similarity with Cosine Distance

Cosine similarity evaluates how close two vectors are.

Process:

- Compute dot product
- Normalize vector lengths
- Output similarity score (0 to 1)

Higher score → stronger conceptual relation.

Example:
- Related fruits → high similarity
- Unrelated objects → low similarity

This enables semantic search.

---

# 5. Secure API Key Handling

API keys must be managed safely.

Options:

Temporary:
```
export KEY=value
```

Permanent:
- Add to `.bashrc`

Never expose keys in public repositories.

---

#  6. Multimodal Embeddings

Multimodal embeddings represent:

- Text
- Images

in the same vector space.

This allows:

- Image-to-text matching
- Cross-format similarity
- Visual content search

Useful for applications like discourse Q&A with images.

---

#  7. Using External Embedding APIs

Multimodal embeddings were demonstrated using an external provider.

Steps:

- Generate API key
- Send text/image
- Receive embedding vector
- Compute similarity score

Matching image and text produced high similarity values.

---

#  8. Role of Vector Databases

Vector databases:

- Store embedding vectors
- Support fast nearest-neighbor search
- Scale semantic retrieval systems

They are essential for building production RAG pipelines.

---

# 9. Document Chunking Strategy

Large documents exceed model limits.

Solution: Divide content into chunks.

Chunking process:

- Split markdown files
- Limit tokens per chunk (e.g., 4096)
- Assign unique identifiers
- Generate embeddings per chunk

This makes retrieval efficient.

---

#  10. Retrieval-Augmented Generation (RAG)

RAG combines retrieval with generation.

Workflow:

1. Convert question into embedding
2. Compare with stored chunk embeddings
3. Retrieve most relevant chunks
4. Pass them to GPT
5. Generate final response

This ensures grounded and accurate answers.

---

#  11. Optimizing Top-K Retrieval

Retrieving Top-K similar chunks balances:

- Accuracy
- Speed
- Cost

Smaller K → faster  
Larger K → more context but higher token usage  

Top-5 worked well in most tests.

---

#  12. Deployment & Debugging

Common problems:

- Repository not public
- Incorrect project URL
- Expired API tokens
- Missing environment variables

Proper configuration is essential.

---

#  13. Importance for Project 1

This session directly supports:

- Semantic search systems
- Discourse-based Q&A
- Documentation assistants
- Efficient API usage

Embeddings + chunking + RAG form the foundation of the project.

---

## Week 3 – Session 2 Concepts Completed 🎉

