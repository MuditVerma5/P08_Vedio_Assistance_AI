# AI Meeting Assistant
This is the improved version of my old Rag-based-project. 
A meeting/video assistant that transcribes audio, translates between Hindi and English, and lets you chat with the content using a Retrieval-Augmented Generation (RAG) pipeline — all wrapped in a simple Streamlit UI.

## Features

- **Audio/Video ingestion** — pull audio directly from a YouTube URL, or work with local audio/video files.
- **Speech-to-Text via Sarvam AI** — transcription is handled by Sarvam AI's speech-to-text API (Saarika model), which is well suited to Indian languages including Hindi.
- **Hindi ⇄ English translation** — automatic translation of transcripts using a lightweight Google-backed translator.
- **LLM-powered summarization & Q&A** — orchestrated with LangChain (LCEL) and powered by the Mistral API.
- **RAG pipeline** — transcripts are chunked, embedded with HuggingFace sentence-transformer models, and stored in a local ChromaDB vector store so you can ask questions grounded in the actual meeting content.
- **Export** — save summaries/transcripts as PDF or TXT.
- **Streamlit UI** — simple browser-based interface, no separate frontend needed.

## Tech Stack

| Layer | Tools |
|---|---|
| Audio/Video acquisition | yt-dlp, pydub, ffmpeg-python |
| Speech-to-Text | Sarvam AI API (Saarika model), called via `requests` | OpenAI
| Translation | deep-translator |
| LLM orchestration | langchain, langchain-core, langchain-community, langchain-mistralai, mistralai |
| RAG / Vector store | chromadb, sentence-transformers, langchain-huggingface, huggingface-hub, tiktoken |
| UI | streamlit, streamlit-extras, watchdog |
| Export | reportlab, fpdf2 |
| Utilities | python-dotenv, numpy, tqdm, requests |
