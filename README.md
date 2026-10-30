# JARVIS Core — Autonomous Self-Healing Infrastructure & Enterprise AIOps Platform

## 📌 Overview
JARVIS Core is a cloud-native B2B autonomous infrastructure (AIOps) and cyber-resilience platform. Engineered for enterprise engineering teams and DevSecOps departments, the platform unites proprioceptive telemetry with generative AI. Built around an asynchronous 49-node microkernel architecture, the system performs real-time execution friction analysis, autonomous patch synthesis and verification via AST (Abstract Syntax Tree), and 6-tier Zero-Trust runtime protection powered by Microsoft Azure.

## 📺 Live Demo Walkthrough

[![Watch JARVIS Core Demo](https://img.youtube.com/vi/DxVsB2mJfKs/maxresdefault.jpg)](https://youtu.be/DxVsB2mJfKs)

> 🔗 **Watch on YouTube:** [JARVIS Core — Autonomous Code Mutation & Zero-Downtime Hot-Swap Demo](https://youtu.be/DxVsB2mJfKs)  
> *Demonstrating live stack-trace capture, AST patch synthesis, automated validation against 24 safety axioms, human-in-the-loop authorization, and zero-downtime hot-swapping.*

## 🏗️ Architecture & Microsoft Azure Infrastructure
Engineered strictly in accordance with the Microsoft Azure Well-Architected Framework to ensure reliability, cost predictability, and zero-trust security:
- **Dual-Tier AI Orchestration:** Powered by **Azure OpenAI Service**. The heavy cognitive tier (`GPT-4o`) executes two-phase Chain-of-Thought planning and AST patch surgery; the low-latency tier (`GPT-4o-mini`) handles real-time intent routing and memory crystallization.
- **Compute & Core Runtime:** Hosted on **Azure Virtual Machines / AKS (Linux)** for isolated execution of the asynchronous microkernel and ChromaDB vector store.
- **Proprioceptive Event Bus:** Asynchronous IPC pipeline (port 49152) guaranteeing sub-250ms dispatching and preventing hardware or asynchronous thread starvation (`Async Starvation`).
- **Client Delivery & Control:** Modular FastAPI and WebSocket interfaces integrated with a holographic engineering dashboard (WarRoom) for Human-in-the-Loop mutation approval.

## 🏛️ System Architecture & Repository Layout

```text
jarvis-core/
├── core/                                # Central coordination & dispatching subsystem
│   ├── main_engine/
│   │   ├── boot_sequence.py             # System bootstrap & integrity verification
│   │   ├── dynamic_loader.py            # Dynamic hot-reloading module watchdog
│   │   ├── entrypoint.py                # Main application entry point
│   │   ├── event_bus.py                 # Asynchronous high-throughput IPC bus
│   │   ├── memory_bridge.py             # Working memory to SQLite persistent bridge
│   │   ├── state_machine.py             # System finite state machine
│   │   └── time_syncer.py               # Precision tick synchronization
│   ├── cognitive/
│   │   ├── cognitive_stream.py          # Real-time context coordination
│   │   ├── ego_anchor.py                # System invariants & priority enforcement
│   │   ├── habit_engine.py              # Automated operational routines
│   │   ├── salience_gate.py             # Signal importance filter
│   │   └── working_memory.py            # High-speed working memory stack
│   └── brain_cells/
│       ├── gemini_engine.py             # Azure OpenAI Dual-Pipeline Controller (GPT-4o / GPT-4o-mini)
│       ├── hot_context.py               # LTM to STM Hot context cache
│       ├── intent_router.py             # Semantic intent & visual command classification
│       ├── logic_evaluator.py           # Multi-tier decision validator
│       └── spatial_router.py            # Network & memory routing
│
├── security_shield/                     # 6-Tier AegisCore & resource safeguards
│   ├── aegis/
│   │   ├── aegis_core.py                # Endpoint protection core
│   │   ├── file_monitor.py              # FIM (File Integrity Monitoring)
│   │   ├── ransomware_lock.py           # SQLite WAL protection engine
│   │   └── process_guard.py             # Process integrity & heartbeat guard
│   ├── atomic_writer.py                 # Transactional atomic configuration writer
│   ├── axioms.py                        # 24 Immutable structural code axioms
│   ├── disk_warden.py                   # Storage space & quota manager
│   ├── env_loader.py                    # Secure zero-trust credential loader
│   └── identity_check.py                # Biometric & cryptographic access verification
│
├── evolution/                           # AST Surgery & autonomous self-healing lab
│   ├── auto_forge.py                    # Analytical module generator
│   ├── bottleneck_profiler.py           # Latency & async starvation profiler
│   ├── reflection_engine.py             # Historical error evaluation & reflection
│   ├── quarantine/
│   │   └── sandbox_env.py               # Isolated runtime for AST-patched code testing
│   └── sandbox/
│       ├── ast_surgeon.py               # Abstract syntax tree surgical analyzer
│       ├── atomic_rollback.py           # Instant state rollback engine
│       └── test_forge.py                # Automated axiom stress testing pipeline
│
├── memory/                              # Distributed cognitive & RAG storage
│   ├── palace_engine/
│   │   ├── compressor.py                # AAAK Chronological Context compression
│   │   └── hybrid_search.py             # Hybrid vector & lexical RAG search
│   ├── storage/
│   │   └── chroma_vault/                # Vector storage (ChromaDB)
│   └── wings/
│       ├── chronos_warden.py            # Temporal synchronization manager
│       ├── ltm_core.py                  # SQLite Long-term pattern memory
│       └── biometry.py                  # Identity contextual integration
│
├── sensory/                             # Input streams & proprioceptive collectors
│   ├── speech/
│   │   ├── acoustic_controller.py       # Audio capture & ducking controller
│   │   ├── speech_decoder.py            # Groq LPU Whisper transcription
│   │   └── speech_synth.py              # Edge-TTS neural voice synthesis
│   └── telemetry/
│       ├── desktop_observer.py          # Host environment & visual screenshot telemetry
│       ├── face_id.py                   # InsightFace CPU biometric detector
│       └── vital_monitor.py             # CPU, RAM & EventBus friction monitor
│
├── web/                                 # Operator Holographic WebHUD (WarRoom)
│   ├── css/
│   │   └── hud.css                      # Telemetry dashboard styles
│   ├── js/
│   │   ├── core_api.js                  # WebSocket client for real-time telemetry
│   │   └── telemetry_canvas.js          # Interactive data canvas
│   └── index.html                       # Engineering WebHUD entry point
│
├── .env.example                         # Environment configuration template
├── .gitignore                           # Excluded secrets, binaries & local DBs
├── requirements.txt                     # Project dependencies (Azure-Native)
└── README.md
🛠️ Technology Stack
Core Engine: Python 3.11+, AsyncIO, FastAPI, WebSockets

Cloud Infrastructure & AI: Microsoft Azure (Azure OpenAI Service, Azure VMs / AKS)

Hybrid Knowledge Base: ChromaDB (Vector RAG), SQLite WAL (Structured long-term persistence)

Architectural Paradigm: Autonomous self-healing microservices via AST mutation and 24 immutable safety axioms

📅 Roadmap
Phase 1 (Q3 2026): 49-Node microkernel architecture, high-throughput IPC bus, and 6-tier AegisCore shield [COMPLETED]

Phase 2 (Q4 2026): Migration of mutation pipeline to Microsoft Azure OpenAI (GPT-4o & GPT-4o-mini) [IN PROGRESS]

Phase 3 (Q1 2027): Multi-tenant B2B SaaS gateway with native GitHub Actions & Azure DevOps CI/CD webhooks

Phase 4 (Q2 2027): Multi-region Azure deployment (swedencentral & westeurope) and Microsoft Azure Marketplace listing

📄 License & Commercial Status
Proprietary B2B Software. Actively maintained and developed for enterprise engineering operations. All rights reserved.
