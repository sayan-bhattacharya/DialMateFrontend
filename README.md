# Dialmate CallCopilot Frontend

<div align="center">

[![React](https://img.shields.io/badge/Frontend-React_18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](src/)
[![Vite](https://img.shields.io/badge/Bundler-Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)](vite.config.js)
[![Tailwind](https://img.shields.io/badge/Styling-Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](tailwind.config.js)

**The dedicated, low-latency agent client interface for DialMate CallCopilot.**

</div>

---

## 📌 System Architecture

```mermaid
graph TD
    classDef client fill:#eff6ff,stroke:#1e40af,stroke-width:2px;
    classDef state fill:#f0fdf4,stroke:#15803d,stroke-width:2px;
    classDef api fill:#fefce8,stroke:#a16207,stroke-width:2px;

    subgraph UserInterface ["🖥️ React Component Hierarchy"]
        CallView[Live Call Telemetry View]
        EmotionRadar[Real-Time Emotion Radar Chart]
        SuggestionCard[AI Agent Coaching Suggestions]
    end

    subgraph StateManagement ["⚡ Client Event Loop"]
        AudioBuffer[WebRTC / Audio Streaming Buffer]
        SocketListener[WebSocket / EventStream Dispatcher]
    end

    subgraph CoreBackend ["🌐 Dialmate Backend & Inference Engine"]
        REST[Express API Gateway :5001]
        FlaskInference[LLaMA-2 Emotion Model :5000]
    end

    CallView --> AudioBuffer
    AudioBuffer --> REST
    REST --> FlaskInference
    FlaskInference --> SocketListener
    SocketListener --> EmotionRadar & SuggestionCard

    class CallView,EmotionRadar,SuggestionCard client;
    class AudioBuffer,SocketListener state;
    class REST,FlaskInference api;
```

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/sayan-bhattacharya/DialMateFrontend.git
cd DialMateFrontend

# Install dependencies
npm install

# Start development server
npm run dev
```

---

## 📬 Contact

- **DialMate AI**: [dialmateai.com](https://dialmateai.com)
- **Author**: Sayan Bhattacharya ([sayanpm17@gmail.com](mailto:sayanpm17@gmail.com))
