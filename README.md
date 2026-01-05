# Simple LLM Application with LCEL

This repository contains a simple end-to-end LLM application built with LangChain using the LangChain Expression Language (LCEL).
The project demonstrates how to build, chain, and deploy a language model pipeline using FastAPI, LangServe, and a Streamlit client.

The main use case implemented is text translation from English into a target language using a Groq-hosted LLM.

## Features

- Simple LLM pipeline built with LCEL
- PromptTemplates and OutputParsers
- Groq LLM integration (LLaMA models)
- FastAPI backend exposed via LangServe
- Streamlit frontend client
- Environment-based configuration using .env
- Educational notebook for step-by-step learning

## Architecture

Streamlit Client
  -> FastAPI + LangServe
  -> LangChain (LCEL)
  -> Groq LLM
  
## Prerequisites

- Install dependencies:
  pip install -r requirements.txt

- Create a .env file:
  GROQ_API_KEY=your_api_key_here

Optional:
GROQ_MODEL=meta-llama/llama-4-scout-17b-16e-instruct

## Run Backend

uvicorn server:app --reload

Endpoint:
POST /chain/invoke

Payload example:
{
  "input": {
    "language": "Spanish",
    "text": "Hello world"
  }
}

## Run Client

streamlit run client.py

## Notebook

The notebook notebooks/simplellmLCEL.ipynb explains:
- Direct LLM calls
- PromptTemplates
- Output parsing
- LCEL chaining

## Tech Stack

Python, LangChain, LangServe, FastAPI, Streamlit, Groq LLM

## Security

Do not commit .env files.
Keep API keys private.

## License

Educational use only.