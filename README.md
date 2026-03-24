# BIDS → openMINDS Workflow Demo

A Jupyter notebook demonstrating a complete pipeline: download MEG data from OpenNeuro, manage it in BIDS format, and convert to openMINDS metadata.

## Prerequisites

- Python 3.11
- Node.js (for `bids-validator` CLI)

## Installation

### 1. Install uv

[uv](https://docs.astral.sh/uv/) is a fast Python package and project manager.

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

After installation, restart your shell or run:

```bash
source $HOME/.local/bin/env
```

Verify it works:

```bash
uv --version
```

### 2. Install project dependencies

Clone the repo and sync all dependencies (including dev tools like `ipykernel`):

```bash
git clone https://github.com/arunps12/bids-openminds-demo.git
cd bids-openminds-demo
uv sync
```

This creates a `.venv/` virtual environment and installs everything from `uv.lock`.

### 3. Install bids-validator CLI (Node.js)

```bash
npm install -g bids-validator
```

## Usage

Open and run the notebook:

The notebook walks through 7 steps:

1. **Download** one subject from OpenNeuro (ds000248)
2. **Read** raw MEG data with MNE-Python
3. **Re-export** to BIDS using MNE-BIDS
4. **Validate** the BIDS dataset
5. **Visualize** a data segment
6. **Generate** openMINDS metadata with bids2openminds
7. **Validate** the openMINDS output

## Project Structure

```
├── bids_openminds_workflow.ipynb   # Main workflow notebook
├── pyproject.toml                  # Project metadata & dependencies
├── uv.lock                        # Locked dependency versions
├── data_input/                     # Downloaded raw data (gitignored)
├── data_bids/                      # Re-exported BIDS dataset (gitignored)
├── openminds_metadata/             # Generated openMINDS files (gitignored)
└── reports/                        # Validation reports & figures (gitignored)
```