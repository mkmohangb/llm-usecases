# llm-usecases

### [Linkedin](https://www.linkedin.com/blog/engineering/generative-ai/musings-on-building-a-generative-ai-product) Musings on building a Gen AI product
  - Dozens of AI agents - General Knowledge, Career and Job, ...
  - **RAG pipeline**, via which internal APIs are called, and their responses are injected into a subsequent LLM prompt to provide additional context to ground the response.
    - Routing: decides if the query is in scope or not, and which AI agent to forward it to. Examples of agents are: job assessment, company understanding, takeaways for posts, etc.
    - Retrieval: recall-oriented step where the AI agent decides which services to call and how (e.g. LinkedIn People Search, Bing API, etc.).
    - Generation: precision-oriented step that sieves through the noisy data retrieved, filters it and produces the final response.
  - Small models for routing/retrieval, bigger models for generation
  - techniques like **Chain of Thought (CoT)** are very effective at improving quality and **reducing hallucinations**. But they require tokens that the member never sees, hence increasing their perceived latency.
  - Time To First Token (TTFT), Time Between Tokens (TBT)
  - We picked **YAML** because it is less verbose, and hence **consumes fewer tokens** than JSON
  - Wrapping RPC APIs in LLM friendly schema
    
  ![image](https://github.com/mkmohangb/llm-usecases/assets/2610866/115d7f10-dada-484a-95d1-3145c4356c58)

  - 80 to 95% took 4 months


