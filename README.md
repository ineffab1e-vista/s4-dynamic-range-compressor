# S4-DRC: Real-time Dynamic Range Compressor Modeling with S4

This repository contains the official PyTorch implementation for the paper:

**[Modeling Analog Dynamic Range Compressors using Deep Learning and State-space Models](https://arxiv.org/abs/2403.16331)**

This project introduces a novel method for creating high-fidelity digital models of analog dynamic range compressors by analyzing their hardware counterparts. It uses a deep learning model based on the Structured State Space for Sequences (S4) architecture, which is highly effective at modeling long-range dependencies in sequence data.

The resulting model is causal, runs efficiently in real-time, and achieves state-of-the-art quality, as demonstrated on the Teletronix LA-2A analog compressor.

## Key Features

*   **End-to-End Training**: Directly learns the behavior of a dynamic range compressor from audio signals.
*   **S4 Architecture**: Utilizes Structured State Space layers to efficiently model long-term dependencies in the audio waveform.
*   **Real-time & Efficient**: The model is designed to be causal and computationally efficient, making it suitable for real-time audio processing applications.

## Installation

This project is managed with [Pipenv](https://pipenv.pypa.io/en/latest/) and requires Python 3.10.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/s4-dynamic-range-compressor.git
    cd s4-dynamic-range-compressor
    ```

2.  **Install dependencies:**
    Run the following command to create a virtual environment and install all required packages from the `Pipfile`.
    ```bash
    pipenv install
    ```
    *Note: For specific hardware configurations (e.g., NVIDIA CUDA versions), you may need to set up a virtual environment manually and install the dependencies listed in the `Pipfile`.*

## Usage

This project uses the `lightning.pytorch` CLI, which provides a standardized interface for training and evaluation. The main entry point is `s4drc`.

The primary commands are `fit`, `validate`, `test`, and `predict`. All commands require a configuration file.

**To run the training (fit) process:**

```bash
pipenv run python -m s4drc fit --config /path/to/your/config.yaml
```

You can discover all available command-line arguments by running:

```bash
pipenv run python -m s4drc --help
```

The main scripts will automatically handle dataset downloading as needed.

## Citation

If you find this work useful in your research, please consider citing the original paper:

```bibtex
@article{Yin2024ModelingAD,
  title={Modeling Analog Dynamic Range Compressors using Deep Learning and State-space Models},
  author={Hanzhi Yin and Gang Cheng and Christian J. Steinmetz and Ruibin Yuan and Richard M. Stern and Roger B. Dannenberg},
  journal={arXiv preprint arXiv:2403.16331},
  year={2024},
  url={https://arxiv.org/abs/2403.16331},
  doi={10.48550/arXiv.2403.16331}
}
```

## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.
