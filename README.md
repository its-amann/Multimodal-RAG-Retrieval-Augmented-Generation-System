# Multimodal RAG (Retrieval Augmented Generation) System

<div align="center">

![Multimodal RAG](https://img.shields.io/badge/Multimodal-RAG-blue?style=for-the-badge&logo=python)
![Python](https://img.shields.io/badge/python-v3.8+-blue.svg?style=for-the-badge&logo=python)
![OpenAI](https://img.shields.io/badge/OpenAI-API-green?style=for-the-badge&logo=openai)
![PyTorch](https://img.shields.io/badge/PyTorch-red?style=for-the-badge&logo=pytorch)

</div>

<div align="center">
<p>A sophisticated system for multimodal information retrieval and generation</p>
</div>

---

## 🌟 Overview
This project implements a sophisticated Multimodal Retrieval Augmented Generation (RAG) system that processes both video and text data. The system is designed to analyze video content, extract frames, generate transcripts, and perform semantic search across multiple modalities (text and images).

## 📁 Project Structure
```
.
├── 📓 Multimodal RAG.ipynb    # Main implementation notebook
├── 📝 requirements.txt        # Project dependencies
├── 🖼️ _asserts/              # Visualization outputs and results
├── 🎞️ frames/                # Extracted video frames
├── 🔊 audios/                # Extracted audio files
├── 📜 transcripts/           # Generated transcripts
└── 🎥 decision-making-course.mp4  # Source video file
```

## 🚀 Features

### Core Capabilities
- 🎥 **Intelligent Video Processing**
  - Advanced frame extraction
  - Precise keyframe detection
  - High-quality audio separation

- 🔊 **Audio Processing Excellence**
  - Speech-to-text transcription
  - Noise reduction
  - Audio segmentation

- 🧠 **Advanced Embedding Generation**
  - CLIP-based image embeddings
  - Transformer-based text embeddings
  - Cross-modal embedding alignment

- 🔍 **Smart Search & Retrieval**
  - Semantic similarity matching
  - Multi-modal context understanding
  - Relevance ranking

- 🎯 **Query Processing**
  - Natural language understanding
  - Context-aware processing
  - Multi-modal query interpretation

## 🔄 System Workflow

<div align="center">

### High-Level Architecture
```mermaid
graph TD
    subgraph Input
        A[User Query] --> B[Query Processing]
    end

    subgraph Text Processing
        B --> C[Text Similarity Search]
        C --> D[Similar Text Chunks]
        D --> |Top K Chunks| G
    end

    subgraph Image Processing
        D --> E[Image Similarity Search]
        E --> F[Similar Images]
        F --> |Top N Images| G
    end

    subgraph Output Generation
        G[Result Generation]
        G --> H[Final Response]
    end

```

### Detailed Process Flow
```mermaid
sequenceDiagram
    participant U as User
    participant Q as Query Processor
    participant T as Text Engine
    participant I as Image Engine
    participant R as Response Generator

    U->>Q: Submit Query
    Q->>T: Process Query Text
    T->>T: Compute Text Similarities
    T->>I: Pass Similar Text Chunks
    I->>I: Find Related Images
    I->>R: Send Images
    T->>R: Send Text Chunks
    R->>U: Return Combined Response

    Note over T,I: Cross-modal Similarity Computation
    Note over R: Multimodal Response Generation
```
</div>

### Step-by-Step Flow:
1. 📝 **Query Input**
   - User submits a natural language query
   - System preprocesses and embeds the query

2. 🔍 **Text Processing**
   - Searches through transcript embeddings
   - Identifies most similar text chunks
   - Ranks text chunks by relevance

3. 🖼️ **Image Processing**
   - Takes similar text chunks as input
   - Searches through frame embeddings
   - Identifies visually relevant frames

4. 🎯 **Response Generation**
   - Combines relevant text and images
   - Ranks multimodal content
   - Generates coherent response

### 1. Video Processing
The system begins by processing the video file using FFmpeg for frame and audio extraction.

![FFmpeg Processing](/_asserts/ffmpeg%20subprocess%20run.png)
*FFmpeg subprocess execution for media processing*

### 2. Text Processing
The system processes transcripts through tokenization and embedding generation.

![Tokenization](/_asserts/tokenize%20the%20transcribs.png)
*Transcript tokenization process*

![Text Embeddings](/_asserts/text%20embedding%20output%20photo.png)
*Generated text embeddings visualization*

### 3. Image Processing
Frames are processed to generate image embeddings for semantic search.

![Image Embeddings](/_asserts/image%20embedding.png)
*Image embedding generation process*

### 4. Cross-modal Similarity
The system computes cosine similarities between different modalities.

![Cosine Similarities](/_asserts/cosine%20similarities%20output.png)
*Cosine similarity computation results*

### 5. Query Processing
For a given query, the system:
1. Generates query embeddings
2. Finds relevant text chunks
3. Retrieves similar images

![Query Embeddings](/_asserts/for%20%20query%20congnitive%20bias%20got%20embedding.png)
*Query embedding generation*

![Query Similarities](/_asserts/cosine%20similarity%20with%20the%20query.png)
*Query-content similarity computation*

### 6. Results Visualization
The system provides various visualizations for the retrieved results:

![Top Text Matches](/_asserts/top%2010%20match%20text%20idx%20with%20the%20query.png)
*Top 10 matching text segments*

![Similar Images](/_asserts/top%203%20similiar%20images%20to%20the%20text.png)
*Top 3 similar images for the query*

![Retrieved Results](/_asserts/retrivied%20text.png)
*Final retrieved text results*

## 📊 Performance and Results
The system demonstrates effective cross-modal retrieval capabilities:
- 📈 Accurate text chunk retrieval based on semantic similarity
- 🎯 Relevant image frame extraction matching query context
- 🔄 Cross-modal alignment between text and visual content

Each query returns both relevant text segments and associated visual frames, providing a comprehensive multimodal response.

## 📜 License

MIT License

Copyright (c) 2024 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.