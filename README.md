# Deep-Learning-Based Semantic Communication with Semantic-Aware Resource Allocation

## Project Overview

This project focuses on developing a **Deep-Learning-Based Semantic Communication System with Semantic-Aware Resource Allocation** for next-generation wireless networks (6G).

Unlike conventional communication systems, which aim to reconstruct transmitted bits accurately, semantic communication focuses on preserving the meaning and important information of transmitted messages.

The project combines deep learning, Transformer-based semantic encoding and decoding, wireless channel simulation, and intelligent resource allocation to improve communication efficiency.

## Objectives

- Develop a conventional digital communication system as a performance baseline.
- Implement a deep-learning-based semantic communication transceiver.
- Evaluate semantic transmission under AWGN and Rayleigh fading channels.
- Investigate the effect of channel conditions and channel uses on semantic performance.
- Develop semantic-aware resource allocation for multiple users.
- Compare MILP, greedy, fixed-K, conventional, and DNN-based allocation techniques.

## System Architecture

The proposed system consists of three major components:

1. **Conventional Communication System**
   - Huffman source coding.
   - Convolutional channel coding.
   - Digital modulation and demodulation.
   - Wireless channel transmission.
   - BER, BLEU, word accuracy, and semantic similarity evaluation.

2. **Deep-Learning-Based Semantic Communication**
   - Transformer-based semantic encoder.
   - Dense channel encoder.
   - AWGN and Rayleigh fading channel models.
   - Channel equalization.
   - Dense channel decoder.
   - Transformer-based semantic decoder.

3. **Semantic-Aware Multi-User Resource Allocation**
   - Multi-user OFDMA channel modelling.
   - Semantic similarity lookup.
   - Adaptive channel-use selection (K).
   - Mixed-Integer Linear Programming (MILP).
   - Greedy resource allocation.
   - Fixed-K resource allocation.
   - DNN-based allocation through imitation learning.

## Technologies Used

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Deep Learning | PyTorch |
| Numerical Computing | NumPy, SciPy |
| Data Processing | Pandas |
| Visualization | Matplotlib, Seaborn |
| NLP | NLTK, Hugging Face / Sentence Transformers |
| Optimization | SciPy MILP |
| Environment | Google Colab |

## Wireless System Configuration

The simulation uses the following configuration:

| Parameter | Value |
|---|---:|
| Number of users | 8 |
| Number of resource blocks | 16 |
| Resource block bandwidth | 180 kHz |
| Base station transmit power | 30 dBm |
| Cell radius | 500 m |
| Minimum user distance | 35 m |
| Small-scale fading | Rayleigh fading |
| Shadowing standard deviation | 8 dB |
| Noise figure | 7 dB |
| Channel-use configurations | K = 1, 2, 4, 8 |

**Note:** The path-loss and shadowing assumptions should be checked against the wireless model specified in Exercise 1 before making a direct performance comparison.

## Project Methodology

### 1. Conventional Communication

A conventional communication chain is implemented using source coding, channel coding, modulation, wireless transmission, equalization, demodulation, and decoding.

The conventional system serves as the baseline for evaluating the semantic communication approach.

### 2. Semantic Communication

A Transformer-based neural network is used to encode sentences into compact representations.

The encoded representations pass through a simulated wireless channel. At the receiver, the signal is equalized and decoded to reconstruct the transmitted sentence.

The system is evaluated for different values of K:

- K = 1
- K = 2
- K = 4
- K = 8

### 3. Resource Allocation

A multi-user OFDMA environment is considered, where multiple users share a limited number of resource blocks.

Different allocation techniques are investigated:

- MILP adaptive-K allocation.
- Greedy adaptive-K allocation.
- Fixed K = 4 allocation.
- Conventional SNR-based assignment with adaptive K.
- DNN imitation-based allocation.

The DNN allocator learns allocation decisions from MILP-generated training labels and applies feasibility constraints to its predictions.

## Performance Evaluation

The project considers the following performance metrics:

| Metric | Purpose |
|---|---|
| BLEU Score | Measures similarity between reference and reconstructed sentences |
| Word Accuracy | Measures correctly reconstructed words |
| Sentence Embedding Cosine Similarity | Measures preservation of sentence meaning |
| Exact Sentence Recovery | Measures perfect sentence reconstruction |
| Semantic Rate | Measures useful semantic information delivered per second |
| QoS Satisfaction | Measures the percentage of users meeting the required rate |
| Cell-Edge Rate | Evaluates performance of the weakest user |
| Training Loss | Evaluates the learning process of neural networks |

## Results and Visualizations

The implementation generates visualizations for:

1. DNN allocator imitation training.
2. User-resource-block SNR heatmap.
3. Channel power gain heatmap.
4. Semantic similarity versus channel uses.
5. Semantic similarity lookup heatmap.
6. Exact sentence recovery versus SNR.
7. Word accuracy versus SNR.
8. Sentence embedding cosine similarity versus SNR.
9. BLEU score versus SNR.
10. Transformer semantic transceiver training and validation loss.
11. Conventional communication performance.
12. Resource allocation comparison.
13. QoS satisfaction comparison.

Generated figures and tables are saved in the project output directory.

## Installation and Execution

### Step 1: Clone the repository

```bash
git clone https://github.com/Ayushmaantiwari/Network_Band.git
```

### Step 2: Open Google Colab

Upload the project notebook to Google Colab or open it from your GitHub repository.

### Step 3: Install dependencies

Run the dependency installation cell in the notebook.

### Step 4: Execute the notebook

Run the notebook cells sequentially, starting from the configuration and dataset preparation cells.

Two execution modes are provided:

- **QUICK:** For testing the implementation with reduced training and evaluation samples.
- **FULL:** For larger training and evaluation experiments.

For final experiments, use FULL mode and allow sufficient training time.

## Output Directory

The generated results are organized as follows:

```text
semantic_comm_outputs/
│
├── figures/
│   ├── dnn_allocator_training.png
│   ├── allocation_methods.png
│   ├── semantic_resource_allocation_comparison.png
│   └── other performance graphs
│
├── models/
│   ├── dnn_allocator.pt
│   └── trained semantic transceiver models
│
└── tables/
    ├── allocation_summary.csv
    ├── semantic_allocation_comparison.csv
    └── corpus_statistics.csv
```

## Important Experimental Notes

- The QUICK mode is intended for pipeline validation, not final scientific conclusions.
- The semantic similarity threshold directly affects resource allocation feasibility.
- If no user-resource-block pair satisfies the threshold, the corresponding semantic allocation rates can become zero.
- DNN imitation performance depends on the quality and quantity of feasible MILP training samples.
- For a fair conventional-versus-semantic comparison, both systems should use the same test sentences and wireless channel realizations.
- The assumed wireless propagation parameters should be replaced with the exact Exercise 1 parameters if they differ.

## Future Improvements

- Improve semantic encoder and decoder training.
- Investigate more effective semantic similarity metrics.
- Improve DNN allocation accuracy and generalization.
- Introduce more realistic wireless channel conditions.
- Investigate power allocation jointly with resource block assignment.
- Evaluate performance under different user densities and channel conditions.
- Compare against additional optimization-based resource allocation methods.

## Author

**Ayushmaan Tiwari**  
Registration Number: **EE26MR009**  
Indian Institute of Technology Dharwad

**Guided by:** Rahul J. Pandya

## Acknowledgement

This project was developed as part of academic research and practical implementation in deep learning, semantic communication, and wireless resource allocation.

---

**Keywords:** Semantic Communication, Deep Learning, Transformer, 6G, OFDMA, Multi-User Resource Allocation, MILP, DNN, Rayleigh Fading, PyTorch, Wireless Communication.
