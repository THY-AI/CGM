# Code Graph Model (CGM)

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Citation](#citation)

## Introduction

We propose a graph-based framework CGM for real-world SE tasks. Before CGM starts its work, we construct a repository-level code graph to better represent the repository context and its structure by Code Graph Generator. Inspired by the Retrieval-Augmented Generation (RAG) approach, CGM framework is designed as a chain structure consisting of four atomic nodes, termed as R4 (Rewriter, Retriever, Reranker, and Reader) chain for this scenario. Given an issue, the initial input to the CGM framework includes the issue description and the corresponding code graph. Rewriter will first rewrite the original issue by extracting keywords and generating relevant queries for code graph. Then a heuristic code subgraph is retrieved through Retriever based on the matching anchor nodes from rewriter output. Given that the resulting subgraph provides a relatively broad context necessary for reference, we need a Reranker to identify the files most likely to be modified as a further hint. Subsequently, both the retrieved subgraph and the identified files are input into a trainable, graph-based Reader to generate the corresponding code patch.

## Features
:white_check_mark: **Code Graph**: Train models on multiple tasks while maintaining a balance between them. The models can even generalize to new, previously unseen tasks.

:white_check_mark: **Multi-framework**: It provides support for both Accelerate (with Deepspeed and FSDP)

:white_check_mark: **Efficient fine-tuning**: It supports LoRA, QLoRA as well as Full-parameters training, enabling fine-tuning of large models with minimal resources. The training speed meets the demands of almost all fine-tuning scenarios.

## Installation
Before installation, make sure you have the following
- Python 3.8
- pip
The required package list are
```plain_text
transformers==4.46.1
tokenizers==0.20.0
accelerate==1.0.1
peft==0.13.2
jinja2==2.11.3
fuzzywuzzy==0.18.0
python-Levenshtein==0.25.1
```
You can simply install with
```plain_text
pip install -r requirements.txt
```

## Usage

## Contributing
Contributions are welcome! If you have any suggestions, ideas, bug reports, or new model/feature supported, please open an issue or submit a pull request.

## License
Distributed under the Apache License 2.0. See ```LICENSE``` for more information.

## Citation
TBD
