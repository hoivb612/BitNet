C:\llama.cpp\bitnet.master>git clone --recursive https://github.com/hoivb612/bitnet .
Cloning into '.'...
remote: Enumerating objects: 74, done.
remote: Counting objects: 100% (71/71), done.
remote: Compressing objects: 100% (52/52), done.
remote: Total 74 (delta 23), reused 50 (delta 14), pack-reused 3 (from 1)
Receiving objects: 100% (74/74), 1.86 MiB | 27.24 MiB/s, done.
Resolving deltas: 100% (23/23), done.
Submodule '3rdparty/llama.cpp' (https://github.com/Eddie-Wang1120/llama.cpp.git) registered for path '3rdparty/llama.cpp'
Cloning into 'C:/llama.cpp/bitnet.master/3rdparty/llama.cpp'...
remote: Enumerating objects: 25519, done.
remote: Total 25519 (delta 0), reused 0 (delta 0), pack-reused 25519 (from 1)
Receiving objects: 100% (25519/25519), 56.23 MiB | 28.92 MiB/s, done.
Resolving deltas: 100% (18452/18452), done.
Submodule path '3rdparty/llama.cpp': checked out '406a5036f9a8aaee9ec5e96e652f61691340fe95'
Submodule 'kompute' (https://github.com/nomic-ai/kompute.git) registered for path '3rdparty/llama.cpp/ggml/src/kompute'
Cloning into 'C:/llama.cpp/bitnet.master/3rdparty/llama.cpp/ggml/src/kompute'...
remote: Enumerating objects: 9118, done.
remote: Counting objects: 100% (253/253), done.
remote: Compressing objects: 100% (148/148), done.
remote: Total 9118 (delta 119), reused 192 (delta 95), pack-reused 8865 (from 1)
Receiving objects: 100% (9118/9118), 17.57 MiB | 43.68 MiB/s, done.
Resolving deltas: 100% (5739/5739), done.
Submodule path '3rdparty/llama.cpp/ggml/src/kompute': checked out '4565194ed7c32d1d2efa32ceab4d3c6cae006306'

=============================================

Llama.cpp Architecture

The architecture of Llama.cpp is a thoughtful adaptation of the original LLaMa models, incorporating several key innovations that distinguish it from conventional transformer models:

Pre-normalization: Unlike the post-normalization technique commonly found in traditional transformer architectures, Llama.cpp adopts a pre-normalization strategy. This involves normalizing the input of each transformer sub-layer, which has been shown to improve training stability and model performance. The use of RMSNorm, a variant of layer normalization, is pivotal in this approach, contributing to more stable and efficient training processes.

SwiGLU Activation Functions: Llama.cpp replaces the standard ReLU activation functions with SwiGLU (Swish-Gated Linear Unit) activation functions. This change is inspired by advancements in neural network design and is instrumental in enhancing the model's capacity to capture complex patterns and relationships within the data. The SwiGLU function has been credited with significant performance improvements in various language processing tasks.

Rotary Embeddings: Another notable feature of Llama.cpp's architecture is the incorporation of rotary positional embeddings (RoPE). This technique marks a departure from the absolute positional embeddings found in many transformer models, offering a more dynamic way to encode sequence positions. Rotary embeddings contribute to a better understanding of word order and positional context, which is crucial for the nuanced comprehension and generation of text.

Together, these architectural choices underscore Llama.cpp's innovative approach to LLM implementation. By integrating these advanced features, Llama.cpp not only adheres to the foundational principles of transformer models but also pushes the boundaries, enhancing model performance and broadening the potential for practical applications.

Key Parameters:

model_path: Specifies the path to the LLM model file you intend to use.
prompt: The input text or question you're providing to the model for generating responses.
max_tokens: The maximum number of tokens (words or pieces of words) the model will generate in its response.
temperature: Influences the randomness of the output. Lower values make the model more deterministic, while higher values encourage creativity.
top_p: Controls the diversity of generated responses by only considering the top p percent of probability mass.
n_gpu_layers: (For GPU users) Determines how many layers of the model should be offloaded to the GPU, optimizing performance.


