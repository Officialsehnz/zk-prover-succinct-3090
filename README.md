**Author:** \[Sehnz]
**Date:** June 2025

* [Twitter:] (https://x.com/tradewithsehnz)
* [Discord:] @officialsehnz

Let's hit it

# 🧪 Succinct Prover Node – Stage 2.5 Participation

This repository documents my technical participation in the **Succinct Labs Stage 2.5 Testnet**, the most advanced proving phase of Succinct’s modular zkVM (SP1). This stage introduces an end-to-end proving economy, where high-performance provers generate zero-knowledge proofs on-demand in a competitive environment powered by auction-based task allocation.

---

## 🚀 Overview – What is Stage 2.5?

Succinct Labs is pushing the boundaries of zero-knowledge computing with **SP1**, a modular zkVM optimized for performance, composability, and developer accessibility.

**Stage 2.5** is the bridge between a closed benchmarking environment (Stage 2) and full onchain prover decentralization (Stage 3). It simulates:
- Real-time proving requests from decentralized applications (dApps).
- A network of independent provers submitting bids to win proving tasks.
- Efficient proof generation using GPUs (primarily NVIDIA RTX 3090 or better).
- Metrics tracking, leaderboard competition, and test incentives.

This phase is intended to simulate a sustainable, decentralized proving economy by closely mimicking future mainnet dynamics.

---

## 💡 Why You Can’t Use a CPU

The **SP1 prover** from Succinct is purpose-built to run efficiently on **CUDA-enabled GPUs**. Here's why CPUs aren’t sufficient:

| Feature | CPU | GPU |
|--------|-----|-----|
| Parallel Processing | Low (few cores) | Massive (thousands of CUDA cores) |
| zk Circuit Processing Speed | Slow | Fast |
| Memory Bandwidth | Limited | High (esp. for RTX 3090+) |
| Proof Generation Time | 10x slower | Optimal |
| Power Efficiency per proof | Worse | Much better |

Zero-knowledge proof generation, especially for general-purpose programs via zkVMs, requires highly parallelized operations such as FFTs, MSMs, and large field arithmetic – operations that modern GPUs like the **RTX 3090, A6000, 4090, etc.** are extremely well-optimized for.

Attempting to generate proofs with a CPU will result in extremely long proving times, failure to compete in auctions, or complete ineligibility due to timeout thresholds in the testnet logic.

---

## 🖥️ Minimum Hardware Requirements

To run a viable proving node for Stage 2.5, the following specs are recommended:

| Component | Minimum Requirement |
|----------|---------------------|
| **GPU** | RTX 3090 (24GB VRAM) or better |
| **CUDA Support** | CUDA 11.7+ |
| **CPU** | 8-core or higher (e.g., Ryzen 7 or Intel i7) |
| **RAM** | 32GB minimum |
| **Disk** | 100GB SSD minimum |
| **OS** | Ubuntu 22.04 / WSL2 with NVIDIA support |
| **Power Supply** | 750W–1000W (to sustain GPU draw) |
| **Network** | Stable, high-uptime internet for auction participation |

The RTX 3090 consumes around **350W under full load**, and can raise electricity costs significantly if running 24/7. It also produces considerable heat, so good ventilation or cooling is essential.

---

## 🔋 Power & Cost Considerations

Running an RTX 3090 24/7 for proving can consume:
- **~8.4 kWh/day**, which at $0.15/kWh = ~$1.26/day just in electricity.
- Over 30 days, that’s ~$37.8/month in energy costs alone (excluding system and internet).

You must factor in:
- GPU rental or purchase cost
- Power bills
- Time-based rewards vs proof completion rate
- Downtime for thermal throttling or system instability

If you're planning to rent GPUs, efficiency matters. Make sure your node can generate proofs *fast enough* to win tasks regularly.

---

## ☁️ Where to Get RTX 3090 or Higher (Cheap)

To participate without owning a physical GPU, cloud solutions are your best option:

### 🔄 GPU Cloud Rental (Pay-per-hour)
- **Vast.ai** – ~$0.15–0.18/hr for RTX 3090 (varies by provider)
- **Genesis Cloud** – ~$0.20/hr, with consistent performance and no hidden fees
- **RunPod**, **Salad Cloud**, **Paperspace** – RTX 3090/4090 often available
- **CloudFerro** – Enterprise-focused but has spot deals

You can run a prover node for **as low as $3–4/day**, meaning ~$90–120/month total compute spend depending on uptime.

### 🛒 Used GPU Marketplaces
If you're buying:
- **eBay, Newegg (Used/Open Box), Aliexpress**
- Local options like **Jiji (Nigeria), Facebook Marketplace, OLX, Craigslist**
- Watch out for power degradation in ex-mining cards – always verify VRAM health and temps

Used RTX 3090s can be found from **$600–$850**, with A6000/4090 models going up to $1.3k–$1.7k.

---

## 🧰 Prover Setup – What to Expect

Succinct’s documentation for Stage 2.5 is gradually being rolled out to whitelisted participants. From past setups, you’ll need:

### 🔧 General Setup Flow
1. Install Docker and NVIDIA Container Toolkit
2. Pull the SP1 prover container
3. Configure your prover identity (`prover_key`, `ETH_PRIVATE_KEY`, etc.)
4. Allocate your GPU to the container (`--gpus all`)
5. Start the prover and connect to the auction scheduler
6. Monitor jobs, logs, and proof validity rate

Scripts, environment files, and log parsing tools will be added to this repo once I'm whitelisted and provisioned.

---

## 📅 How Long Will Stage 2.5 Last?

Succinct Labs has hinted at **Stage 2.5 running for 4–8 weeks**, maybe starting officially in late June 2025. Based on this, GPU rental should ideally be aligned to:
- **1-month minimum**: For early leaderboard and reward qualification
- **2-month maximum**: If planning to extract maximum participation ROI

After Stage 2.5, we expect a transition to **Stage 3 (Mainnet)**, where real PROVE tokens and native incentives will launch.

---

## 📈 Performance Tips

- **Use Linux (or WSL2)** for better GPU passthrough.
- **Always monitor with `nvidia-smi`** – temps should stay <85°C.
- Consider **undervolting** or using **power limit tools** like MSI Afterburner.
- Log proof durations and optimize for short turnaround time.

---

## 📚 Resources

- [Succinct Docs](https://docs.succinct.xyz/)
- [SP1 GitHub](https://github.com/succinctlabs/sp1)
- [Vast.ai GPU Search](https://vast.ai)
- [Genesis Cloud GPU Pricing](https://genesiscloud.com)

---

