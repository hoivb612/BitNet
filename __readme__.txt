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

============================================

D:\llama.cpp\bitnet>d:\Python39\python.exe utils\codegen_tl2.py --model bitnet_b1_58-3B --BM 160,320,320 --BK 96,96,96 --bm 32,32,32

D:\llama.cpp\bitnet>git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        include/bitnet-lut-kernels.h
        include/kernel_config.ini


================================


D:\llama.cpp\bitnet\build>cmake .. -DBITNET_X86_TL2=ON -T ClangCL -DCMAKE_C_COMPILER=clang -DCMAKE_CXX_COMPILER=clang++
-- The C compiler identification is Clang 19.1.5 with MSVC-like command-line
-- The CXX compiler identification is Clang 19.1.5 with MSVC-like command-line
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/Program Files/Microsoft Visual Studio/2022/Community/VC/Tools/Llvm/x64/bin/clang-cl.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/Program Files/Microsoft Visual Studio/2022/Community/VC/Tools/Llvm/x64/bin/clang-cl.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD
-- Performing Test CMAKE_HAVE_LIBC_PTHREAD - Failed
-- Looking for pthread_create in pthreads
-- Looking for pthread_create in pthreads - not found
-- Looking for pthread_create in pthread
-- Looking for pthread_create in pthread - not found
-- Found Threads: TRUE
-- Found Git: C:/Program Files/Git/cmd/git.exe (found version "2.50.1.vfs.0.0")
-- Found OpenMP_C: -Xclang -fopenmp (found version "5.1")
-- Found OpenMP_CXX: -Xclang -fopenmp (found version "5.1")
-- Found OpenMP: TRUE (found version "5.1")
-- OpenMP found
-- Using llamafile
-- Warning: ccache not found - consider installing it for faster compilation or disable this warning with GGML_CCACHE=OFF
-- CMAKE_SYSTEM_PROCESSOR: AMD64
-- CMAKE_GENERATOR_PLATFORM:
-- x86 detected
-- Performing Test HAS_AVX_1
-- Performing Test HAS_AVX_1 - Failed
-- Performing Test HAS_AVX_2
-- Performing Test HAS_AVX_2 - Success
-- Performing Test HAS_AVX2_1
-- Performing Test HAS_AVX2_1 - Failed
-- Performing Test HAS_AVX2_2
-- Performing Test HAS_AVX2_2 - Success
-- Performing Test HAS_FMA_1
-- Performing Test HAS_FMA_1 - Failed
-- Performing Test HAS_FMA_2
-- Performing Test HAS_FMA_2 - Success
-- Performing Test HAS_AVX512_1
-- Performing Test HAS_AVX512_1 - Failed
-- Performing Test HAS_AVX512_2
-- Performing Test HAS_AVX512_2 - Success
-- Configuring done (38.1s)
-- Generating done (0.5s)
-- Build files have been written to: D:/llama.cpp/bitnet/build

D:\llama.cpp\bitnet\build>


================================

D:\llama.cpp\bitnet\build>cmake --build . --config RelWithDebInfo --target llama-cli llama-bench
MSBuild version 17.14.14+a129329f1 for .NET Framework

  1>Checking Build System
  Generating build details from Git
  -- Found Git: C:/Program Files/Git/cmd/git.exe (found version "2.50.1.vfs.0.0")
  Building Custom Rule D:/llama.cpp/bitnet/3rdparty/llama.cpp/common/CMakeLists.txt
  build_info.vcxproj -> D:\llama.cpp\bitnet\build\3rdparty\llama.cpp\common\build_info.dir\RelWithDebInfo\build_info.lib
  Building Custom Rule D:/llama.cpp/bitnet/3rdparty/llama.cpp/ggml/src/CMakeLists.txt


================================

C:\llama.cpp\bitnet>git submodule add https://github.com/XbGH-MS/llama-lut.cpp XbGH-MS/
Cloning into 'C:/llama.cpp/bitnet/XbGH-MS'...
remote: Enumerating objects: 22239, done.
remote: Total 22239 (delta 0), reused 0 (delta 0), pack-reused 22239 (from 1)
Receiving objects: 100% (22239/22239), 44.76 MiB | 49.45 MiB/s, done.
Resolving deltas: 100% (15792/15792), done.
warning: in the working copy of '.gitmodules', LF will be replaced by CRLF the next time Git touches it

C:\llama.cpp\bitnet>type .gitmodules
[submodule "3rdparty/llama.cpp"]
        path = 3rdparty/llama.cpp
        url = https://github.com/Eddie-Wang1120/llama.cpp.git
        branch = merge-dev
[submodule "XbGH-MS"]
        path = XbGH-MS
        url = https://github.com/XbGH-MS/llama-lut.cpp


=================================

C:\llama.cpp\bitnet>git submodule status
 40ed0f290203a9a78540b8f7eb18bd828043fe21 3rdparty/llama.cpp (b3639-321-g40ed0f29)
+1b67cfb20f07792fe8c54569aa3e1d528f3db2c2 XbGH-MS (heads/hv/cpf)

C:\llama.cpp\bitnet>git submodule update --remote --merge

C:\llama.cpp\bitnet>git status
On branch hv/cpf
Your branch is up to date with 'origin/hv/cpf'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
  (commit or discard the untracked or modified content in submodules)
        modified:   3rdparty/llama.cpp (modified content)
        modified:   XbGH-MS (new commits)

no changes added to commit (use "git add" and/or "git commit -a")

C:\llama.cpp\bitnet>git add XbGH-MS

C:\llama.cpp\bitnet>git status
On branch hv/cpf
Your branch is up to date with 'origin/hv/cpf'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   XbGH-MS

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
  (commit or discard the untracked or modified content in submodules)
        modified:   3rdparty/llama.cpp (modified content)


C:\llama.cpp\bitnet>git commit -m "Update XbGH-MS to latest commit"
[hv/cpf e0814a8] Update XbGH-MS to latest commit
 1 file changed, 1 insertion(+), 1 deletion(-)

C:\llama.cpp\bitnet>git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 32 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 263 bytes | 263.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: This repository moved. Please use the new location:
remote:   https://github.com/hoivb612/BitNet.git
To https://github.com/hoivb612/bitnet
   193a216..e0814a8  hv/cpf -> hv/cpf

C:\llama.cpp\bitnet>git status
On branch hv/cpf
Your branch is up to date with 'origin/hv/cpf'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
  (commit or discard the untracked or modified content in submodules)
        modified:   3rdparty/llama.cpp (modified content)

no changes added to commit (use "git add" and/or "git commit -a")

C:\llama.cpp\bitnet>



