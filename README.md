
**Summary:**

I implemented a seq2seq model with attention designed for machine translation tasks. Here's a breakdown of the model architecture and its parameters:

- **Vocabulary and Embeddings:** The baseline model utilizes a vocabulary of roughly 12,000 words, corresponding to around a third of the available data. These words are transformed into embeddings with a 64-dimensional space. Although I tested various embedding dimensions, the 64-dimensional space consistently yielded the best results.

- **Encoder:** The encoder is structured around a bidirectional GRU with a hidden size of 128. After processing the input data, the encoder's output undergoes transformation by a linear layer to produce a 128-dimensional output.

- **Decoder:** The decoder layer employs the same 64-dimensional embeddings as the encoder. It takes as its input the previously predicted token. Following this, the attention mechanism's output is directed into a uni-directional GRU. Subsequently, this output is processed through two linear layers. Notably, one of these linear layers functions as a pointer-generator and features a softmax activation function.

**Observations:**

1. With an increase in both the data size and vocabulary, I noticed a marked improvement in the accuracy of the predicted summaries. This is especially evident from the reduction in "UNK" tokens in the summaries.
2. There's a discernible decrease in training and validation losses when the model is trained over an increasing number of epochs.
3. However, post reaching a specific threshold of epochs, there isn't any significant decline in the loss, which suggests a potential underfitting scenario.

By meticulously combining different components, adjusting parameters, and making observations, I've worked towards optimizing the model's performance.  After the training phase, I employed the "evaluate.py" script for an in-depth assessment of the model's predictions, ensuring that I met or exceeded baseline performance metrics.
