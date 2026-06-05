# MediScan
AI powered breast cancer detection from histopathological images using EfficientNet -B0 (NOT CONFIRMED YET, could still use ResNet) with attention mechanisms and Grad-CAM to make it easily interpretable.

## Overview

Mediscan uses convolutional neural networks to classify breast tissue histopathological images as benign or malignant. Mediscan gives interpretable predictions through Grad-CAM heatmaps that highlight the regions that helped Mediscan determine each classification decision.

## Tech Used
- Python 3.11
- Pytorch / fastai
- EfficientNet -B0
- Grad-CAM / Grad-Cam++
- Streamlit (web interface)
- VS Code
- Google Colab
- Github
- OBS Studio


## Datasets
- BreakHis (Breast Cancer Histopathological Database)
- CBIS-DDSM (Curated Breast Imaging Subset of Digital Database for Screening Mammography)

## Project Timeline
- Summer of 2026 (Summer before sophomore year): Environment Setup, Learning Python, Train first CNN on BreakHis
- Sophomore Year 2026-2027: Pipeline development with Efficient-B0 and Google Colab, Grad-CAM, and Accuracy Improvements
- Summer of 2027 (Summer after sophomore year): Add CBIS-DDSM Dataset to MediScan, Implement Attention Mechanisms like Squeeze-and-Excitation (SE) blocks and CBAM (Convolutional Block Attention Module) into EfficientNet-B0
- Junior Year 2027-2028: Competition Submissions, web interface with Streamlit, and publicize a paper.
- Summer of 2028 (Summer after Junior Year): Create a Demo Video of MediScan's Streamlit with OBS Studio and Deploy MediScan on streamlit.