# AI Meeting Assistant with Multi-Agent Collaboration

An AI-powered meeting assistant that brings specialized virtual agents into online meetings (Google Meet, Zoom, and Microsoft Teams) to provide real-time feedback, design reviews, engineering insights, QA recommendations, and meeting summaries.

## Overview

This project integrates meeting automation, conversational AI, speech processing, and multi-agent collaboration into a unified platform. Each agent is designed to represent a specialized role such as:

* CEO Advisor
* Engineering Manager
* Senior Designer
* QA Lead
* Security Officer
* DevOps Engineer
* Product Reviewer
* Retrospective Facilitator

Agents can join meetings, listen to discussions, generate contextual responses, and collaborate with participants in real time.

## Key Features

### AI Agent Collaboration

* Multiple specialized AI agents
* Role-specific reasoning and responses
* Context-aware conversations
* Real-time meeting participation

### Meeting Integration

* Google Meet support
* Zoom support
* Microsoft Teams support
* Automated meeting joining

### Speech Processing

* Real-time speech recognition
* Transcript generation
* Voice-based responses
* Speaker interaction tracking

### Automation Framework

* Event-driven architecture
* Automated workflow orchestration
* Multi-agent communication layer
* Session management

### Dashboard

* Web-based control panel
* Agent selection interface
* Team presets
* Live monitoring

## Technical Architecture

The platform consists of:

* Python Backend
* Web Dashboard
* Agent Runtime Layer
* Speech Processing Engine
* Meeting Integration Layer
* Multi-Agent Communication Bus

### Technologies Used

* Python
* JavaScript
* HTML/CSS
* WebSockets
* REST APIs
* Speech Recognition
* AI/LLM Integration
* Automation Workflows

## Installation

Clone the repository:

```bash
git clone https://github.com/kartik-yadav123/AI_meeting-assistant-.git
cd AI_meeting-assistant-
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the application:

```bash
python server.py
```

Open:

```text
http://localhost:8765
```

## Project Highlights

* Multi-agent AI architecture
* Real-time meeting automation
* Speech-to-text processing
* Event-driven communication
* Web-based dashboard
* Scalable agent orchestration

## Future Enhancements

* Meeting summarization
* Action-item extraction
* Google Workspace integration
* Calendar scheduling automation
* Analytics dashboard
* Enterprise deployment support

## Author

**Kartik Yadav**

B.Tech, Electronics and Communication Engineering

Interested in AI Automation, Workflow Engineering, FPGA Systems, and Intelligent Software Platforms.

## License

MIT License
## Repository Structure

```text
gstack-joins-meeting/
├── README.md                # Project documentation
├── SKILL.md                 # Brain-loop instructions for Claude
├── CLAUDE.md                # Project-level Claude instructions
├── ARCHITECTURE.md          # Data flow and architecture details
├── CONTRIBUTING.md          # Contribution guidelines
├── SECURITY.md              # Security findings and mitigations
│
├── install                  # One-line installer
├── server.py                # Dashboard server and API endpoints
├── specialist_runner.py     # Runtime for specialist agents
├── index.html               # Dashboard frontend
├── specialists.js           # Auto-generated specialist registry
│
├── data/                    # Specialist and team definitions
├── avatars/                 # Character avatars and assets
├── avatar-page/             # Avatar rendering interface
├── vendor/                  # AgentCall bridge integrations
├── scripts/                 # Launch and utility scripts
├── bin/                     # Diagnostic tools
│
└── hosted/                  # Optional SaaS deployment wrapper
```

### Deployment Modes

| Mode        | Features                   | Startup Time |
| ----------- | -------------------------- | ------------ |
| Avatar Mode | Voice + Animated 3D Avatar | ~30 seconds  |
| Audio Mode  | Voice Only                 | ~10 seconds  |

Avatar mode serves visual avatars through a local web server and AgentCall WebSocket relay, allowing each specialist to appear as a unique animated participant inside the meeting.

---

## System Architecture

The platform consists of:

1. **Dashboard Server (`server.py`)**

   * Handles specialist dispatching
   * Session orchestration
   * Recall management
   * REST endpoints

2. **Specialist Runtime (`specialist_runner.py`)**

   * Executes specialist workflows
   * Manages bot lifecycle
   * Handles communication channels

3. **Intelligence Bus**

   * Shared inbox for transcripts
   * Per-agent outbox queues
   * Agent communication layer

4. **Meeting Integration Layer**

   * AgentCall bridge
   * WebSocket communication
   * Voice synthesis
   * Real-time interaction

---

## Troubleshooting

### Bot joins but remains silent

Possible causes:

* Audio context failed to initialize
* Browser audio permissions blocked
* Voice service unavailable

Recommended actions:

```bash
python server.py
```

Try switching to Audio Mode if Avatar Mode is experiencing audio issues.

---

### Bot responds once and stops

Possible causes:

* Intelligence loop not running
* Transcript stream disconnected
* Claude session not monitoring messages

Verify system status:

```bash
bash bin/brain-status.sh
```

---

### Multiple bots speak simultaneously

Possible causes:

* Synchronization lock failure
* Interrupted session cleanup

Reset active sessions:

```bash
bash scripts/kill-session.sh
```

---

### Dispatch succeeds but no bot appears

Check orchestration logs:

```bash
sessions/session-latest/orchestrator.log
```

Common causes:

* Invalid AgentCall API key
* Authentication failure
* Network connectivity issues

---

### Recall command fails

Terminate all active specialist sessions:

```bash
bash scripts/kill-session.sh
```

Then restart the dashboard and dispatch the specialists again.
