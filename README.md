# RAG Blueprint

An interactive, developer-focused sandbox demonstrating a production-ready Enterprise Retrieval-Augmented Generation (RAG) architecture. 

This application serves as a living Technical Design Document (TDD). It visually exposes the internal states, microservice data payloads, LLM gateway failover mechanisms, and observability metrics required to run a compliant, resilient AI system at an enterprise scale.

## ✨ Core Features

* **Interactive Pipeline Trace:** Watch a query move step-by-step through Auth, Context Management, Embedding, Vector Retrieval, and LLM Generation.
* **Live Payload Inspector:** Click on any pipeline execution step to view the exact JSON HTTP requests and responses (roles, vector arrays, retrieved context, and generation parameters) moving between services.
* **LLM Gateway Resiliency:** Simulate primary provider timeouts and watch the system automatically trip circuit breakers and route to a fallback model.
* **Reactive Observability Stack:** Monitor dynamic UI charts that track simulated cost per request, retrieval vs. generation latency, and human-in-the-loop feedback metrics.
* **Advanced RAG Configurations:** Tweak parameters like Top-K chunk retrieval, Temperature, and system prompts to see exactly how they alter the generated context window and final output.
* **TDD Blueprint Mode:** Toggle architectural overlays that map specific UI components directly to the underlying Design Document guidelines.

## 🏗️ Architecture Overview

The system is designed around a three-layer foundation-model-centric architecture:

1. **Application Layer:** Manages conversational state, access control, and user feedback mechanisms.
2. **Model Layer:** Wraps external foundation model APIs behind a unified gateway, handling multi-model routing, prompt construction, and vector database querying.
3. **Infrastructure Layer:** Handles asynchronous background indexing jobs, document parsing, and the observability stack (metrics/logs).

## 🚀 Getting Started

To run the RAG Blueprint sandbox locally:

### Prerequisites
* Node.js 18.x or higher
* npm or yarn

### Installation

1. Clone the repository:
   ```bash
   git clone [[https://github.com/yourusername/rag-blueprint.git](https://github.com/yourusername/rag-blueprint.git)](https://github.com/babupallam/rag-blueprint.git)
   cd rag-blueprint
````

2.  Install dependencies:

    ```bash
    npm install
    # or
    yarn install
    ```

3.  Start the development server:

    ```bash
    npm run dev
    # or
    yarn dev
    ```

4.  Open [http://localhost:3000](https://www.google.com/search?q=http://localhost:3000) with your browser to see the result.

## 🧪 How to Use the Demo

Once the app is running, use these scenarios to test the architecture's capabilities:

**1. The Happy Path (Standard RAG Data Flow)**

  * Type a query like *"What is the new 2024 remote work policy?"* in the chat window.
  * Watch the **Pipeline Trace** move through each microservice.
  * Check the **Payload Inspector** to see the vector embeddings and retrieved document chunks.

**2. Testing Gateway Failover (Risk Mitigation)**

  * Open the **Config Service** (gear icon).
  * Toggle on **"Simulate Primary Provider Timeout"**.
  * Send another message in the chat.
  * Observe the intentional pipeline failure and the subsequent automatic routing to the Fallback Provider, along with the `504` and `200` HTTP codes in the payload inspector.

**3. Adjusting Data Flow Parameters**

  * Open the **Config Service**.
  * Change the **Top-K** slider from 2 to 4.
  * Send a message and click the "Retriever" step in the pipeline trace. The Payload Inspector will now show an array of exactly 4 retrieved documents.

**4. Monitoring Observability**

  * Click the "Thumbs Up/Down" buttons on system responses.
  * Open the **Infrastructure & Observability** drawer at the bottom of the screen to watch the Feedback donut chart update in real-time, alongside your simulated query latency.

## 🛠️ Tech Stack

  * **Framework:** Next.js (TypeScript)
  * **Styling:** Tailwind CSS
  * **Icons:** Lucide React
  * **Charts:** Recharts

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.

```
