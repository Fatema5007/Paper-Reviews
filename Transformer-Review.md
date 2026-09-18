# Attention Is All You Need Paper Study Notes

This study explores the landmark 2017 paper by Ashish Vaswani et al. introducing the Transformer architecture, with a core focus on understanding how sequence transduction models can be built entirely on attention mechanisms, completely dispensing with recurrence and convolutions.

The main problem addressed in the paper is that traditional sequence modeling tasks, such as machine translation, heavily relied on complex Recurrent Neural Networks (RNNs) like LSTMs or Gated Recurrent Units (GRUs) connected with an encoder-decoder structure. These sequential models inherently suffer from a major limitation: computation cannot easily be parallelized across training examples because they process data step-by-step (sequentially). This makes it very difficult to scale effectively on large datasets.

To solve this sequential bottleneck, the authors introduced the Transformer, a novel architecture that relies solely on attention mechanisms to draw global dependencies between input and output without using sequence-aligned RNNs or convolutions. The core of this model is the "Scaled Dot-Product Attention" and "Multi-Head Attention", which allow the model to jointly attend to information from different representation subspaces at different positions simultaneously. 

Additionally, the architecture utilizes Positional Encoding because the model contains no recurrence or convolution, meaning it has no inherent sense of word order; positional encodings are added to the input embeddings to inject information about the relative or absolute position of the tokens in the sequence.

The framework was evaluated primarily on machine translation tasks (WMT 2014 English-to-German and English-to-French translation), where it achieved superior translation quality while requiring significantly less time to train compared to existing architectures of that era. This breakthrough laid the fundamental groundwork for modern Large Language Models (LLMs) and multi-modal models like Vision Transformers.
