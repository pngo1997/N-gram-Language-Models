# 📖 N-Gram Language Modeling & Text Generation  

## 📜 Overview  
This project focuses on **N-gram language modeling** using a subset of the **One Billion Word Language Modeling Benchmark**. The tasks include:  

1. **Building N-gram models** (unigram, bigram, trigram) from a training corpus.  
2. **Evaluating the models** using **perplexity**, with and without **Laplace smoothing**.  
3. **Generating text** using different N-gram models with various sampling strategies.  

📌 **Key Concepts Covered**:  
- **N-gram Models**: Unigram, Bigram, Trigram  
- **Conditional Frequency Distributions**  
- **Perplexity Calculation**  
- **Laplace Smoothing**  
- **Text Generation Techniques**  

## 🚀 1️⃣ Implementation Details  

### **Part I: N-Gram Modeling & Perplexity Evaluation**  

✅ **Data Processing**:  
- Use **whitespace tokenization** (no preprocessing needed).  
- Build vocabulary:  
  - Replace words occurring **<3 times** with `<unk>`.  
  - Add `<START>` at sentence beginnings and `<STOP>` at sentence ends.  

✅ **N-gram Model Construction**:   
- Use **NLTK’s `ngrams()` function** to create N-grams.  
- Store probabilities using **NLTK’s `ConditionalFreqDist`**.  

✅ **Perplexity Evaluation**:  
- Implement `perplexity()` **without smoothing**.  
- Implement `perplexity_laplace()` **with Laplace smoothing**.  
- Compute **log probabilities** to prevent underflow.  
- Compare perplexity scores of **training vs. test sets**.  

📌 **Key Insights**:  
- Laplace smoothing prevents zero probabilities but **increases perplexity**.  
- Higher-order N-grams provide **better context but require more data**.
  
### **Part II: Text Generation with N-Gram Models**  
✅ **Train models using combined training + test set**.  
✅ **Generate sentences** using different strategies:  
  1️⃣ **Greedy choice** (selects the most probable next word).  
  2️⃣ **Random sampling** (chooses the next word randomly).  
  3️⃣ **Top-p nucleus sampling** (randomly samples from a subset of probable words).  
✅ **Termination criteria**: Stop after **100 words** or upon encountering `<STOP>`.  

📌 **Observations**:  
- **Greedy choice** produces repetitive and predictable text.  
- **Random sampling** generates diverse but sometimes nonsensical text.  
- **Top-p nucleus sampling** balances coherence and diversity.  

## 📊 2️⃣ Results & Analysis  

### **Perplexity Scores**  
- For non-smoothing, among three ngrams models, it shows that trigram performs best with the lowest perplexity. The pattern is consistent between train and test data where the higher the n-gram model, better output. For Laplace smoothing, the output was predictable for bigram and trigram, since Laplace smoothing includes unseen context count, the high perplexity results emphasize that the model was over robust, aka. introduces a large number of unseen n-grams.
Notably, looking at unigram for both smoothing methods, unigram output pretty much stay the same. This indicates that Laplace smoothing has little to no effect when the context is limited to the word itself. 

![Perplexity](https://github.com/pngo1997/Images/blob/main/Ngram.png)  

## 📌 Summary  
✅ Built Unigram, Bigram, and Trigram models.

✅ Evaluated models using perplexity (with & without Laplace smoothing)*.

✅ Generated text using multiple sampling techniques. 

✅ Compared results for linguistic insights.
