# English-to-Vietnamese Transformer Model

This project is a sequence-to-sequence Transformer model, built from scratch using PyTorch, designed to translate English sentences into Vietnamese.

## ✨ Key Features

- **Custom Transformer:** Implements the full Transformer architecture (Encoder-Decoder, Positional Embeddings, Word Embeddings) using `torch.nn.Transformer`.
- **Specialized Tokenization:** Uses **NLTK** for English tokenization and **`underthesea`** for accurate Vietnamese word segmentation.
- **Custom Vocabulary:** Builds separate source (EN) and target (VI) vocabularies from the corpus, handling `<pad>`, `<bos>`, `<eos>`, and `<unk>` tokens.
- **Masking:** Correctly implements source/target padding masks and look-ahead (causal) masks for the decoder.
- **Evaluation:** Uses the `sacrebleu` library to calculate the BLEU score for a comprehensive evaluation of translation quality.
- **Inference:** Includes a `decode_greedy` function for efficient translation of new sentences.

## ⚙️ Tech Stack

- **Core:** Python, PyTorch
- **Data Handling:** Pandas
- **NLP Tokenization:** NLTK (English), `underthesea` (Vietnamese)
- **Evaluation:** `sacrebleu`, Matplotlib

## 🚄 Model Architecture

The model is a standard Transformer architecture with the following parameters:

- **Encoder Layers:** 4
- **Decoder Layers:** 4
- **Embedding Dimension (`embed_dim`):** 512
- **Number of Heads (`num_heads`):** 8
- **Feed-Forward Dimension (`ff_dim`):** 512

## 📦 Dataset

The model was trained on a parallel corpus of **150,000 English-Vietnamese sentence pairs**. The original data files can be found here:

- **English Sentences:** `https://drive.google.com/file/d/1bUy3KTl8S-D1Qc9nYJUBnaRXElevdoMF/view`
- **Vietnamese Sentences:** `https://drive.google.com/file/d/1F4WFFlA1ceZuGNoqPhXj5cx3fmQbEd15/view`

## 📊 Results

The model's performance was tracked by comparing training loss against validation loss per epoch. The final translation quality is measured by the corpus BLEU score.

![Training vs Validation Loss](assets/training_loss_plot.png)
- **Final BLEU Score:** 29.3303

## 🚀 How to Run

### Option 1: Google Colab (Recommended)

The easiest way to run this project is by opening the Google Colab notebook directly. You can "Save a copy in Drive" and run all cells.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1iXALveHBoVQiErvz8uAVJcMhOJS7QKMX)

### Option 2: Run Locally (Not Recommended)

**. Environment Setup**
This project was built using:
* **Python:** `3.10+`
* **PyTorch:** `2.0+`
* **Key Libraries:** `pandas`, `underthesea`, `nltk`, `sacrebleu`
  
1.  Clone the repository.
2.  Install dependencies: `pip install pandas torch underthesea matplotlib nltk sacrebleu`
3.  Download the dataset files and update the paths in the script.
4.  Run the Python script (or notebook). The script includes sections for data loading, training, evaluation, and testing custom sentences.
