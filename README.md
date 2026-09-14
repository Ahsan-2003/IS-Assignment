# AI-Powered Network Intrusion Detection System (NIDS)

## Project Overview
This repository contains a proof-of-concept Machine Learning solution designed for **SecureNet Corp** to augment the existing Network Intrusion Detection System (NIDS). Developed for Information Security (CLO 4), this tool automatically classifies real-time network traffic as either benign activity or specific threat vectors (such as DDoS and Brute-Force attacks).

## Technical Implementation Highlights

- **Handling File Size Limitations:** Full public NIDS datasets (e.g., CIC-IDS2017) span several gigabytes and cannot be processed in standard local memory without causing `MemoryError` crashes. This implementation extracts a representative subset (`nrows=100000`) using pandas or generates structured synthetic traffic signatures to ensure stable execution without hardware exhaustion.

- **Mitigating Class Imbalance:** To prevent high false-negative rates where severe attack classes go completely undetected, the workflow applies `stratify=y` data splitting alongside `class_weight='balanced'` inside the Random Forest estimator.

## How to Run

1. Clone this repository:

```bash
git clone https://github.com/abdullahwaseem404/IS-Assignment-1.git
