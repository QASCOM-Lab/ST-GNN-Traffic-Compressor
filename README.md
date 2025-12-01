# 🌐 ST-GNN-Traffic-Compressor: Spatio-Temporal Graph Neural Networks for Latency-Aware Bandwidth Optimization

**QASCOM Lab Initiative** | **[Associated Publication: Graph Neural Networks for Traffic Classification in Satellite Communication Channels (Proceedings of Telecommunication Universities, 2023)]**

[![DOI Badge]](https://doi.org/10.31854/1813-324X-2023-9-3-14-27)
[![GitHub Stars]](https://github.com/QASCOM-Lab/ST-GNN-Traffic-Compressor/stargazers)
[![License: MIT]](https://opensource.org/licenses/MIT)
[![Docker Build]](https://hub.docker.com/r/qascom/st-gnn-compressor)

---

### 🚀 Overview

The `ST-GNN-Traffic-Compressor` leverages the unique capabilities of **Spatio-Temporal Graph Neural Networks (ST-GNNs)** to model and optimize data flows within dynamic Hybrid Satellite-Terrestrial Networks (HSTN). By treating the network as a dynamic graph, the system can predict future traffic loads and topology changes, enabling proactive decisions on data compression and traffic prioritization.

This project is essential for realizing **latency reduction** and maximizing the utilization of scarce satellite bandwidth, particularly for critical data streams like UAV video feeds or remote command-and-control signals.

### 💡 Key Features & Technical Contributions (PoC Focus)

1.  **ST-GNN Architecture:** Implementation of GNN architectures (e.g., Graph Convolutional Networks (GCN) combined with Temporal Convolutional Networks (TCN) or LSTM layers) specifically adapted to handle the spatial variability and temporal evolution of NTN graphs.
2.  **Traffic Feature Engineering:** Module for extracting essential features from network flows (e.g., packet size, inter-arrival time) and mapping them onto graph nodes and edges for GNN input.
3.  **Adaptive Compression Module:** A decision-making engine that uses the ST-GNN's predictions to intelligently apply adaptive data compression techniques (e.g., lossy compression for low-priority video, lossless for telemetry) based on current network congestion and priority.
4.  **NTN Dataset Utilities:** Scripts to generate synthetic or process real-world network datasets reflecting the characteristics of satellite and ground link traffic.

### 📈 Business & Research Impact Showcase

This framework offers significant optimization potential for operators and service providers:

*   **Bandwidth Efficiency:** Demonstrates how intelligent GNN-based prioritization can significantly reduce overall bandwidth consumption while maintaining Quality of Service (QoS) for high-priority traffic.
*   **Latency Minimization:** Quantifies the reduction in end-to-end latency achieved by preemptive traffic management and compression, crucial for enabling time-sensitive applications over satellite links.
*   **Predictive Management:** Provides a model capable of predicting future congestion points and topology shifts, moving network management from reactive to proactive.

### ⚙️ Setup and Reproducibility (Dockerized)

The simulation environment is easily deployed via Docker, ensuring all PyTorch Geometric, network simulation, and GNN dependencies are handled automatically.

**Prerequisites:** Docker and Docker Compose must be installed.

#### Step 1: Clone the Repository

```bash
git clone https://github.com/QASCOM-Lab/ST-GNN-Traffic-Compressor.git
cd ST-GNN-Traffic-Compressor
```

#### Step 2: Build the Environment

```bash
# Build the Docker image
docker build -t qascom-st-gnn:latest .
```

#### Step 3: Run Training and Evaluation

```bash
# Run training on a sample satellite traffic dataset
docker run qascom-st-gnn:latest python src/train_st_gnn.py --epochs 50

# Run evaluation and latency analysis
docker run qascom-st-gnn:latest python src/evaluate_compression.py
```

### 🗺️ Project Roadmap

| Phase | Goal | Status |
| :--- | :--- | :--- |
| **V1.0 (Current)** | Implementation of basic GNN for traffic classification on static satellite link data. | *Planning* |
| **V1.1 (Q1 2026)** | Integration of the Temporal component (TCN/LSTM) to create the full ST-GNN model. Dataset utilities for dynamic graph generation. | *Planned* |
| **V2.0 (H1 2026)** | Full implementation of the Adaptive Compression Module. Benchmarking end-to-end latency against standard queue management algorithms. | *Planned* |

### 📚 Associated Publications

This repository is the official code base for experiments conducted in:

*   **Graph Neural Networks for Traffic Classification in Satellite Communication Channels: A Comparative Analysis**
    *   *P. H. Do, T. D. Le, A. Berezkin, R. Kirichek*
    *   **[Read the Journal Article]** (Link to DOI/Journal)
*   *Other research focusing on latency reduction in NTN using AI.*

### 🤝 Contribution

We welcome contributions related to graph theory, network optimization, and GNN model efficiency. Please see the `CONTRIBUTING.md` file for details.
