top (right after the title), as you requested:
Markdown---
name: Skycom AI Setup Guide
description: Complete guide for Skycom project + Local AI environment (Open WebUI + Ollama)
---

# Skycom AI Setup Guide

## Most Used Docker Compose Commands

```bash
# 1. Start all services (Ollama + Qdrant + Open WebUI)
docker compose up -d

# 2. Stop all services
docker compose down

# 3. Stop and remove all data (use with caution)
docker compose down -v

# 4. Restart the entire stack
docker compose down && docker compose up -d

# 5. View logs
docker compose logs -f
docker compose logs -f ollama
docker compose logs -f open-webui

# 6. Restart specific service
docker compose restart ollama
docker compose restart open-webui

# 7. Check status of containers
docker compose ps

# 8. Start + follow Ollama logs immediately
docker compose up -d && docker compose logs -f ollama

---
name: Skycom Recommended Ollama Models
description: Best models for 40GB RAM CPU-only laptop
---

# Recommended Ollama Models for Skycom Project

**Laptop Specs**: 40GB RAM, No GPU (CPU-only)

This list is optimized for **Ruby on Rails + Stimulus** development with good balance between **coding quality** and **speed**.

### Model Comparison Table

| Priority | Model Tag                          | Approx. RAM Usage | Expected CPU Speed | Best For                                      | Pull Command |
|----------|------------------------------------|-------------------|--------------------|-----------------------------------------------|--------------|
| 1        | `qwen2.5-coder:7b`                | 5–7 GB           | 10–20 t/s         | **Best daily driver** – Excellent coding + usable speed | `ollama pull qwen2.5-coder:7b` |
| 2        | `qwen2.5-coder:3b`                | 2–3 GB           | 25–45 t/s         | Fast responses, autocomplete, light tasks     | `ollama pull qwen2.5-coder:3b` |
| 3        | `llama3.1:8b` or `llama3.3:8b`    | 5–7 GB           | 8–16 t/s          | Good all-rounder + solid coding               | `ollama pull llama3.1` |
| 4        | `gemma2:9b`                       | 6–8 GB           | 8–14 t/s          | Strong reasoning & writing                    | `ollama pull gemma2:9b` |
| 5        | `phi4:14b`                        | 8–11 GB          | 7–14 t/s          | Excellent reasoning & logic                   | `ollama pull phi4` |
| 6        | `qwen2.5-coder:14b-instruct`      | 9–12 GB          | 3–8 t/s           | Better coding quality (when you can wait)     | `ollama pull qwen2.5-coder:14b-instruct` |
| 7        | `gemma2:27b`                      | 15–20 GB         | 2–5 t/s           | High quality (slow but powerful)              | `ollama pull gemma2:27b` |

### Quick Start Recommendation

**Pull these 3 models first** (Best balance for your setup):

```bash
ollama pull qwen2.5-coder:7b
ollama pull qwen2.5-coder:3b
ollama pull llama3.1