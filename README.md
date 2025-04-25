# EE412 Homework Programming Assignments

This repository contains implementations for the programming components of EE412 homeworks at KAIST. Below is a breakdown of each assignment that includes code implementation.

---

## HW0 – Spark Word Count

**File:** `hw0.py`  
**Task:**  
- Implement Spark-based word count.  
- Submit the result using `spark-submit`:

```bash
bin/spark-submit hw0.py path/to/input.txt
```

---

## HW1 – Spark + A-Priori + LSH

### 1. Mutual Friends Discovery (Spark)
**File:** `hw1_1.py`  
- Find user pairs who are not friends but share many mutual friends.  
- Output format:
```
<User1><TAB><User2><TAB><Count>
```
- Run with:

```bash
bin/spark-submit hw1_1.py path/to/soc-LiveJournal1Adj.txt
```

### 2. Frequent Itemsets (A-Priori Algorithm)
**File:** `hw1_2_b.py`  
- Implement A-Priori for frequent pairs. Use support threshold 100.  
- Output 12 lines:  
  ```
  <Num Frequent Items>  
  <Num Frequent Pairs>  
  <Item1><TAB><Item2><TAB><Count><TAB><Conf1><TAB><Conf2>
  ```

**File:** `hw1_2_c.py`  
- Find top-10 frequent triples.  
- Output 11 lines in this format:
  ```
  <Num Frequent Triples>  
  <Item1><TAB><Item2><TAB><Item3><TAB><Count><TAB><Conf((1,2),3)><TAB>...
  ```

### 3. Locality-Sensitive Hashing (Minhash)
**File:** `hw1_3.py`  
- Find similar articles using 3-shingles and LSH.  
- Use `b=6`, `r=20`, and cosine similarity threshold ≈ 0.9.  
- Print top-10 similar article pairs with their similarity scores.

---

## HW2 – KMeans + Collaborative Filtering

### 1. KMeans Clustering with Spark
**File:** `hw2_1.py`  
- Cluster 4601 documents with 58 features using Spark.  
- Run with:

```bash
bin/spark-submit hw2_1.py path/to/kmeans.txt <k>
```
- Output: average diameter for given `k`.

### 3. Collaborative Filtering
**File:** `hw2_3b.py`  
- Predict ratings using:
  - User-based CF
  - Item-based CF

```bash
python hw2_3b.py path/to/ratings.txt
```

- Print top-5 predicted movies (for user ID=600, item IDs 1–1000):
  ```
  <MOVIE ID><TAB><PREDICTED RATING>
  ```

---

## HW3 – PageRank + Neural Network + node2vec

### 1. PageRank with Spark
**File:** `hw3_1.py`  
- Run PageRank for 50 iterations with `β = 0.9`.  
- Run with:

```bash
bin/spark-submit hw3_1.py path/to/graph.txt
```

- Output top-10 pages:
  ```
  <PAGE_ID><TAB><SCORE>  # 5 decimal places
  ```

### 2. MNIST Classification (NN from scratch)
**File:** `hw3_2_p3.py`  
- Fully-connected NN (1 hidden layer) for 10-class MNIST classification.  
- Use sigmoid activation + MSE loss.  
- Run with:

```bash
python hw3_2_p3.py path/to/training.csv path/to/testing.csv
```

- Output:
  ```
  <TRAIN ACC>
  <TEST ACC>
  <ITERATIONS>
  <LEARNING RATE>
  ```

### 3. node2vec with DFS walk
**File:** `hw3_3_p3.py`  
- Deterministic node2vec with DFS sampling.  
- Use:
  - N=128, W=2, L=5, K=3, learning rate=0.01

```bash
python hw3_3_p3.py path/to/graph.txt
```

- Output: 128-dim embedding for node 5 and 10, print 1st element with 5 decimal places.

---

> ⚠️ **Note:** Every homework submission requires the `Ethics Oath` file in PDF format.