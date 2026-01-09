# LSTM Text Generation - Interview Task

## 📁 Project Structure

```
📁 Submission
├── 📓 lstm_text_generation.ipynb   ← Main notebook (run this)
├── 📄 README.md                     ← This file
├── 📄 generated_samples.txt         ← Auto-generated after running
├── 📄 project_summary.txt           ← Auto-generated after running
├── 📊 training_history.png          ← Auto-generated after running
└── 📊 architecture_comparison.png   ← Auto-generated after running
```

---

## 🚀 Quick Start (Step-by-Step)

### Step 1: Open Google Colab
1. Go to [Google Colab](https://colab.research.google.com)
2. Sign in with your Google account

### Step 2: Upload Notebook
1. Click **File → Upload notebook**
2. Upload `lstm_text_generation.ipynb`

### Step 3: Enable GPU (Important!)
1. Click **Runtime → Change runtime type**
2. Select **GPU** under Hardware accelerator
3. Click **Save**

### Step 4: Run the Notebook
1. Click **Runtime → Run all**
2. Wait for all cells to complete (~30-45 minutes)
3. Or run cells one by one using `Shift + Enter`

### Step 5: Download Outputs
After running, download these files:
- `generated_samples.txt`
- `training_history.png`
- `architecture_comparison.png`
- `project_summary.txt`

---

## 📊 Dataset Information

**Source:** TensorFlow Shakespeare Dataset

**URL:** https://storage.googleapis.com/download.tensorflow.org/data/shakespeare.txt

**Alternative Sources:**
- [Project Gutenberg - Shakespeare](https://www.gutenberg.org/ebooks/100)
- [Kaggle Shakespeare Dataset](https://www.kaggle.com/datasets/kingburrito666/shakespeare-plays)

The dataset is automatically downloaded when you run the notebook.

---

## 🏗️ Model Architecture

```
Input (100 chars) → Embedding(64) → LSTM(256) → Dropout → LSTM(256) → Dropout → Dense(softmax)
```

### Key Components:
- **Embedding Layer:** Converts characters to 64-dimensional vectors
- **LSTM Layers:** 2 layers with 256 units each
- **Dropout:** 20% dropout for regularization
- **Output:** Softmax over vocabulary

---

## 🔬 Bonus: Architecture Experiments

The notebook includes comparison of 3 architectures:

| Architecture | LSTM Layers | Units | Parameters |
|--------------|-------------|-------|------------|
| Small        | 1           | 128   | ~100K      |
| Medium       | 2           | 256   | ~800K      |
| Large        | 3           | 512   | ~5M        |

---

## 🎯 Interview Tips

Be ready to explain:

1. **Why LSTM over RNN?**
   - LSTMs solve the vanishing gradient problem
   - Better at capturing long-term dependencies

2. **What does the Embedding layer do?**
   - Converts discrete characters to continuous vectors
   - Learns meaningful representations during training

3. **What is Temperature in text generation?**
   - Controls randomness of predictions
   - Low (0.2-0.5): More conservative, predictable
   - High (1.0+): More creative, diverse

4. **Why use categorical crossentropy?**
   - Standard loss for multi-class classification
   - Each character is a class

5. **How does text generation work?**
   - Feed seed sequence → Predict next char → Append → Repeat

---

## 📝 Sample Outputs

After running, you'll see outputs like:

```
Seed: "to be or not to be that is the question..."
Temperature: 0.8

Generated:
"...whether 'tis nobler in the mind to suffer
the slings and arrows of outrageous fortune,
or to take arms against a sea of troubles..."
```

---

## ⚠️ Troubleshooting

| Issue | Solution |
|-------|----------|
| Out of memory | Reduce `BATCH_SIZE` to 64 |
| Training too slow | Use GPU (Runtime → Change runtime type) |
| Poor generation | Train for more epochs or use lower temperature |

---

## 📚 References

1. [LSTM Paper (Hochreiter & Schmidhuber, 1997)](https://www.bioinf.jku.at/publications/older/2604.pdf)
2. [TensorFlow Text Generation Tutorial](https://www.tensorflow.org/text/tutorials/text_generation)
3. [Understanding LSTM Networks](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)

---

**Created for Generative AI Engineer Interview Task**
