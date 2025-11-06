This project is on the basic concepts of data analysis to help beginners get started in thier data analysis journey.


```mermaid
flowchart TD
    %% STYLE DEFINITIONS
    classDef frontend fill:#61dafb,stroke:#333,stroke-width:1px,color:#000
    classDef backend fill:#f4b400,stroke:#333,stroke-width:1px,color:#000
    classDef llm fill:#a142f4,stroke:#333,stroke-width:1px,color:#fff
    classDef data fill:#34a853,stroke:#333,stroke-width:1px,color:#fff
    classDef infra fill:#ff7043,stroke:#333,stroke-width:1px,color:#fff

    FE["Lucas Frontend\n(React + Tailwind UI)"]
    AUTH["Authentication Service\n(FastAPI + JWT)"]
    LLM["LLM Service\n(Lucas ADK + Gemini 2.5 Pro + Flash)"]
    DB["Cloud SQL"]
    MCPS["MCPS Service\n(Model Context Protocol + BigQuery + Redis)"]
    RUNNER["Cloud Runner Service\n(Google Cloud Storage + Orchestration)"]
    GCS["Google Cloud Storage"]

    class FE frontend
    class AUTH backend
    class LLM llm
    class DB data
    class MCPS backend
    class RUNNER infra
    class GCS data

    FE --> AUTH
    AUTH --> LLM
    LLM --> DB
    LLM --> MCPS
    MCPS --> RUNNER
    RUNNER --> GCS