# Base image with CUDA support for PyTorch and TensorFlow (if using GPU)
FROM mcr.microsoft.com/vscode/devcontainers/python:3.10

# Set up environment variables
ENV PYTHONUNBUFFERED=1 \
    CUDA_VISIBLE_DEVICE=-1 \
    DEBIAN_FRONTEND=noninteractive 

# Install dependencies
RUN apt-get update && apt-get install -y \
    git \
    wget \
    unzip \
    libgl1 libglib2.0-0 \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip

# Install PyTorch & TensorFlow
RUN pip install --no-cache-dir torch torchvision torchaudio tensorflow keras \
    comet_ml numpy regex tqdm gym opik openai transformers datasets peft lion-pytorch

RUN pip install --no-cache-dir matplotlib IPython opencv-python

# Set the working directory inside the container
WORKDIR /workspaces/introtodeeplearning

CMD ["/bin/bash"]