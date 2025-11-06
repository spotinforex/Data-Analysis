This project is on the basic concepts of data analysis to help beginners get started in thier data analysis journey.


```mermaid
flowchart TD
    classDef frontend fill:#61dafb,stroke:#333,stroke-width:1px,color:#000
    classDef backend fill:#f4b400,stroke:#333,stroke-width:1px,color:#000
    classDef llm fill:#a142f4,stroke:#333,stroke-width:1px,color:#fff
    classDef data fill:#34a853,stroke:#333,stroke-width:1px,color:#fff
    classDef infra fill:#ff7043,stroke:#333,stroke-width:1px,color:#fff

    FE[Lucas Frontend<br/>(React + Tailwind UI)]:::frontend
    AUTH[Authentication Service<br/>(FastAPI + JWT)]:::backend
    LLM[LLM Service<br/>(Lucas ADK + Gemini 2.5 Pro + Flash)]:::llm
    DB[(Cloud SQL)]:::data
    MCPS[MCPS Service<br/>(Model Context Protocol + BigQuery + Redis)]:::backend
    RUNNER[Cloud Runner Service<br/>(Google Cloud Storage + Orchestration)]:::infra
    GCS[(Google Cloud Storage)]:::data

    FE --> AUTH
    AUTH --> LLM
    LLM --> DB
    LLM --> MCPS
    MCPS --> RUNNER
    RUNNER --> GCS