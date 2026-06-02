# Talk to the Network

A natural language interface for 5G RAN management. Describe what you need in plain English — the system translates it into network actions, delivers real-time KPI data, and explains what is happening in the network.

## Overview

Traditional RAN management requires deep expertise to interpret metrics and tune parameters. This system removes that barrier: operators describe their goals conversationally, and the platform maps intent to network configurations backed by real data and LLM reasoning.

## Features

- **Natural Language Interface** — Describe network goals in plain language
- **Real-Time KPI Monitoring** — Throughput, latency, SINR, packet loss per cell
- **Intent Processing** — Groq LLM maps operator intent to RAN configurations
- **Network Topology View** — Visual map of active RAN nodes
- **Dataset Management** — Browse and filter the underlying 6G HetNet dataset
- **Self-Healing** — Autonomous detection and resolution of network anomalies

## Tech Stack

### Backend
| Component | Technology |
|-----------|-----------|
| Server | Flask (Python) |
| LLM | Groq — Llama 3 |
| Data | Pandas + CSV |
| Dataset | 6G HetNet with geolocation |

### Frontend
| Component | Technology |
|-----------|-----------|
| Framework | Next.js 14 |
| Language | TypeScript |
| Styling | Tailwind CSS |

## Getting Started

### Prerequisites

- Python 3.10+
- Groq API key — [console.groq.com](https://console.groq.com) (free tier available)
- Node.js 18+

### Backend

```bash
# Install dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Add GROQ_API_KEY to .env

# Download dataset (one-time)
python download_dataset.py

# Start backend
python csv_tool.py
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

## Dataset

Uses the 6G HetNet Transmission Management dataset with geolocation metadata, providing realistic RAN node positioning and KPI distributions.

## Deployment

- Backend: [Render](https://render.com) / [Railway](https://railway.app) — Procfile included
- Frontend: [Vercel](https://vercel.com)

## License

MIT License