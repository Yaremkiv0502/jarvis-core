# JARVIS Core — Autonomous Self-Healing Infrastructure & Enterprise AIOps Platform

📌 Огляд
JARVIS Core — це хмарна B2B платформа автономної інфраструктури (AIOps) та кіберзахисту. Розроблена для інженерних команд і DevSecOps-відділів, система поєднує пропріоцептивну телеметрію з генеративним штучним інтелектом. Побудована навколо мікроядерної архітектури на 49 вузлів, платформа в реальному часі аналізує «програмне тертя», автоматично синтезує та тестує код через AST (Abstract Syntax Tree), а також забезпечує шестирівневий захист нульової довіри (Zero-Trust) на базі Microsoft Azure.

🏗️ Архітектура та інфраструктура Microsoft Azure
Платформа спроєктована за стандартами Microsoft Azure Well-Architected Framework для забезпечення надійності, передбачуваності витрат та безпеки:
- **Дворівнева AI-Оркестрація:** Працює на базі **Azure OpenAI Service**. Важкий контур `GPT-4o` відповідає за двофазне планування (Chain-of-Thought) та хірургію коду, а швидкісний `GPT-4.1-mini` маршрутизує інтенції та кристалізує спогади.
- **Обчислення та механізм:** Розміщено на **Azure Virtual Machines / AKS (Linux)** для ізольованого виконання асинхронного ядра та векторного сховища ChromaDB.
- **Пропріоцептивна шина подій:** IPC-магістраль (порт 49152), що гарантує диспетчеризацію менше ніж за 250 мс та відсікає апаратне чи асинхронне голодування (`Async Starvation`).
- **Клієнтська доставка:** Модульні інтерфейси FastAPI та WebSocket з підтримкою голографічного веб-інтерфейсу (WarRoom) для затвердження інженерних мутацій (Human-in-the-Loop).

🏛️ Архітектура системи та макет репозиторію
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
│       ├── gemini_engine.py             # Azure OpenAI Dual-Pipeline Controller (GPT-4o / GPT-4.1-mini)
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

🛠️ Технологічний стек
- Основний рушій: Python 3.11+, AsyncIO, FastAPI, WebSockets
- Хмарна інфраструктура та AI: Microsoft Azure (Azure OpenAI, Azure VMs/AKS)
- Гібридна база знань: ChromaDB (векторний RAG), SQLite WAL (структурований довгостроковий архів)
- Архітектурний шаблон: Асинхронні мікросервіси із самовідновленням коду через AST та 24 аксіоми безпеки.

📅 Дорожня карта (Roadmap)
- Фаза 1 (Q3 2026): Архітектура мікроядра на 49 вузлів, шина подій IPC та 6-рівневий щит AegisCore [ЗАВЕРШЕНО].
- Фаза 2 (Q4 2026): Міграція конвеєра мутацій та синтезу на Microsoft Azure OpenAI (GPT-4o та GPT-4.1-mini) [В ПРОЦЕСІ].
- Фаза 3 (Q1 2027): Запуск багатокористувацького B2B SaaS шлюзу з вебхуками для GitHub Actions та Azure DevOps CI/CD.
- Фаза 4 (Q2 2027): Розгортання мультирегіонального кластера Azure (swedencentral та westeurope) з лістингом в Azure Marketplace.

📄 Ліцензія та статус
Пропрієтарне B2B програмне забезпечення (Proprietary). Активно розробляється для інженерних команд. Усі права захищено.
