# QuarkMedSearch: A Long-Horizon Deep Search Agent for Exploring Medical Intelligence

> **Authors:** Zhichao Lin\*, Zhichao Liang\*, Gaoqiang Liu, Meng Xu, Baoyu Xiang, Jian Xu, Guanjun Jiang  
> **Affiliations:** Qwen Applications Business Group, Alibaba; Shanghai Jiao Tong University  
> **Domain:** Medical Deep Search, Agentic AI, Reinforcement Learning

[![arXiv](https://img.shields.io/badge/arXiv-2604.12867-b31b1b.svg)](https://arxiv.org/abs/2604.12867)

## 📄 Abstract

As agentic foundation models continue to evolve, how to further improve their performance in vertical domains has become an important challenge. To this end, building upon Tongyi DeepResearch, a powerful agentic foundation model, we focus on the Chinese medical deep search scenario and propose **QuarkMedSearch**, systematically exploring a full-pipeline approach spanning medical multi-hop data construction, training strategies, and evaluation benchmarks to further push and assess its performance upper bound in vertical domains.

Specifically:
- **Data Synthesis:** To address the scarcity of deep search training data in the medical domain, we combine a large-scale medical knowledge graph with real-time online exploration to construct long-horizon medical deep search training data.
- **Post-Training:** We adopt a two-stage SFT and RL training strategy that progressively enhances the model's planning, tool invocation, and reflection capabilities required for deep search, while maintaining search efficiency.
- **Evaluation:** We collaborate with medical experts to construct the QuarkMedSearch Benchmark through rigorous manual verification.

Experimental results demonstrate that QuarkMedSearch achieves **state-of-the-art performance** among open-source models of comparable scale on the QuarkMedSearch Benchmark, while also maintaining strong competitiveness on general benchmarks.

## 🏗 Main Framework

The QuarkMedSearch pipeline follows a full-stack approach: **Data Synthesis → Post-Training → Evaluation**.

<p align="center">
  <img src="figures/overview.png" width="100%" alt="Medical Deep Search Task Synthesis Pipeline">
</p>


## 🌟 Core Contributions

*   **Four-Phase Progressive Medical Deep Search Data Synthesis**  
    We propose a four-stage pipeline for constructing long-horizon medical reasoning data: (1) Knowledge Graph-Based Seed Question Construction using long-tail entity sampling; (2) Online Environment-Based Multi-Hop Real-Fact Introduction with retrieval-necessity verification; (3) Entity Obfuscation with multi-round self-iterative checklist optimization; (4) Multi-model Uniqueness and Correctness Guarantee through cross-model validation.

*   **SFT and RLVR Combined Post-Training Recipe**  
    We propose a two-stage post-training recipe combining supervised fine-tuning with reinforcement learning from verifiable rewards. SFT progresses from short (32K) to long (128K) trajectories to establish stable long-horizon search behavior, while RLVR further improves performance under a strict reward design that mitigates reward hacking.

*   **QuarkMedSearch Benchmark**  
    We construct a rigorous testbed for Chinese medical long-horizon deep search with medical experts. It contains **140 human-verified questions** spanning six major categories (Biomedical Fundamentals, Drugs & Medical Products, Medical Research & Knowledge, Diseases & Clinical Manifestations, Clinical Procedures, Medical Institutions), with strict guarantees of answer uniqueness and reasoning depth.

*   **Transfer of Agentic Capabilities to Business Scenarios**  
    We validate that capabilities learned from short-answer medical deep search transfer effectively to medical long-answer generation in real business scenarios, achieving a 72.3% win-or-tie rate against baselines.


## 📖 Citation

If you find this work useful, please consider citing:

```bibtex
@article{lin2026quarkmedsearch,
  title={QuarkMedSearch: A Long-Horizon Deep Search Agent for Exploring Medical Intelligence},
  author={Lin, Zhichao and Liang, Zhichao and Liu, Gaoqiang and Xu, Meng and Xiang, Baoyu and Xu, Jian and Jiang, Guanjun},
  journal={arXiv preprint arXiv:2604.12867},
  year={2026}
}
```