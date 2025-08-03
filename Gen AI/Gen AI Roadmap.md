 Generative AI refers to artificial intelligence systems that can create new content - text, images, code, music, videos, and more - based on patterns learned from training data, mimicking human creativity.

Mental model to learn Generative-AI
Base models are computationally expensive and are created by big companies like Open-Ai, Anthropic. 
How to use these base models as a consumer is a syllabus to learn in Gen-AI:
User perspective involves - RAG, Finetuning, Agentic, Vector databases, Prompt engineering
Builder perspective involves - RLHF, Fine tuning, pretraining, quantization
# Foundational model/ Base model
## A. Builders perspective
	1. Transformer architecture
	2. Types of Transformers
		1. Encoder only (Bert)
		2. Decoder only (LLama, Mistral)
		3. Encoder + Decoder
	3. Pretraining
	4. Optimization
	5. Evaluation
	6. Deployment
## B. User perspective
	1. Building basic LLM Apps
		1. Open source vs closed source LLMs
		2. Using LLM APIs
		3. LangChain
		4. Huggingface 
		5. Ollama
	2. Prompt engineering
	3. RAG
	4. Fine Tuning
	5. Agentic
	6. LLMOps
	7. Misc

![[Pasted image 20250803132516.png | 450]]

 According to Nitesh, LangChain framework of python can achieve everything on the user side of things and also some things on the Builder side of things. Hence learning lang chain can help understand all the parts of Gen-AI, and this will be our origin to start learning Gen-AI.

Topic 1: [[Langchain]]








Phase 1: Prompt Engineering and token management
Goal: learn the art and science of interacting with LLMs

1. Prompt Engineering deepdive
	- Zero shot, few shot, chain of thought
	- Temperature, top_p, tokens, max_length
- Project 2: Smart Email Generator
	- Take a subject and generate email copy
	- use prompt templates and roles
Phase 2: LangChain Essentials
Understand how to built production level using LangChain

1. LangChain Basics
	- Chain, Tools, Agent, Memory, Prompt Templates
- Project3: AI powered PDF Q&A bot
	- Upload PDF-> Chunk it -> Embed -> Query using Open AI
	- Tools: LangChain, FAISS, PyPDF, OpenAI Embeddings
Phase 3: RAG(Retrieval-Augmented Generation)
Goal: Build RAG based systems from scratch
1. Intro to Embeddings and Vector Stores
	- ChromaDB, Pinecone
	- [[Cosine Similarity]], Chunking, Indexing
- Project 4: Resume Analyzer bot
	- Upload Resume, analyze it and suggest job matches
	- RAG Pipeline from Chroma + LangChain
- Project 5: Youtube Video Q&A Bot
	- Use YT-DLP to extract  transcripts
	- Crete Embeddings, and answers based on videos
Phase 4: Agents and Tools
Goal: Use LLMs with tools and create autonomous workflows
1. LangChain Agents Explained
	- ReAct, MRKL, Tool Usage
- Project 6: Multi tool research assistant
	- Toolset: SerpAPI, calculator, WebSearch, DocsReader 
- Project 7: AI Travel Planner
	- Input: Dates + preferences-> Output itinerary
Phase 5: LangGraph and Multi Agent Systems
Goal: Master LangGraph for dynamic multi agent orchesteration
1. LangGraph Intro
	- Graph based reasoning
	- Building agent workflows
- Project 8: Autonomous startups ideation bot
	- One agent ideates, one critiques and one validates market fit
Phase 6: API Deployment + Web App integration
Goal: Serve models via API and Build full stack apps
1. Serving LLM APPs with FastAPI
	- API Routing, auth, JSON I/O
- Project 9: AI Code review API
	- Input: PR diff-> Output review comment suggestion
- Frontend integration(Optional React/Firebase)
	- Connecting FastAPI backend with frontend
	- Deploy on Vercel/Render
Phase 7: MCP (Model Context protocol)
Goal: Personalize LLM Behavior per user Domain or app context

Phase 8: Deployment and Production Ready AI
Goal: take apps to production
1. Caching, rate limiting and logging
	- Redis Pinecone and persistence
	- Tracing with LangSmith/ OpenTelemetry
- Project 10: Full-Stack AI feedback App
	- Input: Student project uploads
	- Output: Instant AI Feedback stored in database
	- Dashboard views with Ranking/scores
Bonus Module (Optional Advanced Topics)
- Finetuning vs RAG
- Open Source LLMs: LLAMA, Mistral, OLLAMA
- Local Vector DBs and Embedding Models (Ex. Instructor-XL )
- Cost optimization techniques (Token counting, streaming)
- Using Hugging Face transformers directly



Ans from a Gen AI Engineer, how to be one:
Hey!

I am a “Gen AI Engineer” :’) so i think i might be able to provide some guidance here. I’ve only talked about text models here. So:

- Learn about the attention mechanism. (No need to deep dive. Just understand what it does).
    
- Transformers vs RNNs vs LSTM/GRU (Again a brief overview should suffice).
    
- Different types of LLMs based on transformers. Encoder-Decoder, Decoder-Decoder, etc. Just skim through what types of architectures are popular LLMs such as GPT 3.5/4, Llama2, Mistral 7B or 8x7B based on.
    
- Open Source vs Closed Source LLMs: Which ones are better at the moment? Different companies involved in the LLM rat race such as OpenAI, Google DeepMind, Mistral, Anthropic, etc. How to access these? For open source explore platforms such as Huggingface and Ollama.
    
- Prompt Engineering: Get comfortable with writing prompts. I would suggest Andrew NGs short course on prompt engineering to understand methods such as few shot learning.
    
- Learn about each of these: What are tokens? What are Vector Embeddings and what are some popular embedding model available today?Why do we need VectorDBs such as FAISS, Pinecone or ChromaDB etc? What does context length of an LLM mean?
    
- What is Quantization of LLM weights? Difference between 4-bit, 8-bit, 16-bit LLMs.
    
- Retrieval Augmented Generation or RAG: Understand how training data used for LLMs might not have all the info you need, RAG allows you to perform question answering on your personal documents. At this point, you might want to explore frameworks such as Langchain anf LlamaIndex. These provide one stop solution for all GenAI related requirements of your application.
    
- Finetuning LLMs: Why do we need to finetune LLMs? How is it different from RAG? How much GPU memory/VRAM would I need to finetune a small LLM such as Llama2? Techniques such as LoRA, QLoRA, PEFT, DPO etc. Finetuning an LLM would require some understanding of frameworks such as Pytorch or tensorflow.
    
- Advanced features such as Agents, Tool use, Funtion calling, Multimodal LLMs, etc.
    
- Access various opensource models such from ollama or huggingface. Also get familiarized with using OpenAI’s API.
    
- I would also suggest try to work with streamlit. It’s a very convenient way of creating a frontend for your application. 
