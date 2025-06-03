# Textbook Pipeline

This repository was created to contain modular, locally runnable pipelines for extracting structured text from scanned textbooks using a combination of OCR, vision-language models (VLMs), and large language models (LLMs).

The goal is to build a clean, searchable corpus for multilingual document analysis using only local infrastructure — no cloud APIs, fully reproducible on platforms like the ALICE HPC cluster at Leiden University or other high-end consumer machines.

## Pipelines (work in progress)

### Pipeline A – OCR-Based
- Converts PDFs to PNGs
- Extracts raw text using EasyOCR (or similar)
- Post-processes output (cleaning, etc.)
- Outputs structured JSON with basic page-level metadata

### Pipeline B – Vision-Language Prototype
- Converts PDF pages to images
- Uses a VLM (e.g., LLaVA-1.5 + Mistral) for direct image-to-text interpretation
- Post-processes output (cleaning, etc.)
- Outputs structured JSON

## Project Goals

- Enable high-quality multilingual corpus creation from scanned, layout-rich documents
- Test OCR-free workflows using modern vision-language models
- Provide scalable, modular tools for researchers in the digital humanities and social sciences

## Technical Environment

This project is built to run on:
- **ALICE HPC cluster** or similar GPU-enabled Linux environments
- **Consumer machines** with hig-end CUDA-capable GPUs

Dependencies include:
- Python ≥ 3.10
- [EasyOCR](https://github.com/JaidedAI/EasyOCR) for OCR extraction [or alternative - e.g., loghi (https://github.com/knaw-huc/loghi)]
- [llama-cpp-python](https://github.com/abetlen/llama-cpp-python) or [llava.cpp](https://github.com/jllllll/llava.cpp) for local model inference
- Quantized weights for LLMs (e.g., EXAONE-70B, EXAONE-7B) and VLMs (e.g., LLaVA-1.5 + Mistral)
- PDF-to-image conversion via `pdf2image`, `PyMuPDF`, or `pdfplumber`

More folders and content will be added as the project develops. Expect piepline changes.

