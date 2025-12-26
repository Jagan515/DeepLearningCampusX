# **Important Training Factors in Deep Learning**

These factors decide **how fast**, **how stable**, and **how well** a model learns.

---

## **1. Learning Rate (LR)** ⭐⭐⭐

### What is it?

Learning rate controls **step size** while updating weights.

* High LR → fast but unstable
* Low LR → slow but stable

### Rule:

> Learning rate is the **most important hyperparameter**

---

## **2. Learning Rate Decay** ⭐⭐⭐

### What is LR Decay?

Gradually **reduce learning rate** as training progresses.

> Big steps in beginning, small steps near minimum

---

### Why LR Decay is Needed

* Prevents overshooting near minimum
* Improves final accuracy
* Stabilizes training

---

### Common Types of LR Decay

#### 1️⃣ **Step Decay**

LR drops after fixed epochs

```
LR = LR × 0.1 every 10 epochs
```

#### 2️⃣ **Exponential Decay**

LR decreases smoothly

```
LR = LR0 × e^(−kt)
```

#### 3️⃣ **Time-Based Decay**

LR decreases with time

```
LR = LR0 / (1 + kt)
```

#### 4️⃣ **Reduce on Plateau**

LR reduces when validation loss stops improving
✔ Most practical

---

### When to Use LR Decay

* Long training
* Deep networks
* High initial learning rate

---

## **3. Batch Size** ⭐⭐

### Meaning

Number of samples processed at once.

| Batch Size | Effect                                 |
| ---------- | -------------------------------------- |
| Small      | Noisy gradients, better generalization |
| Large      | Stable gradients, faster computation   |

**Common values:** 32, 64, 128

---

## **4. Number of Epochs** ⭐⭐

### Meaning

One full pass through dataset.

* Too few → underfitting
* Too many → overfitting

Use **Early Stopping** to stop automatically.

---

## **5. Weight Initialization** ⭐⭐

Bad initialization → training fails.

| Activation | Initialization |
| ---------- | -------------- |
| tanh       | Xavier         |
| ReLU       | He             |

---

## **6. Regularization Techniques** ⭐⭐

### 1️⃣ **L2 Regularization (Weight Decay)**

Penalizes large weights
Prevents overfitting

### 2️⃣ **Dropout**

Randomly drops neurons
Forces robust learning

### 3️⃣ **Batch Normalization**

Stabilizes activations
Allows higher learning rate

---

## **7. Optimizer Choice** ⭐⭐⭐

| Optimizer | Use Case        |
| --------- | --------------- |
| SGD       | Simple problems |
| Momentum  | Faster SGD      |
| NAG       | Avoid overshoot |
| AdaGrad   | Sparse data     |
| RMSProp   | Noisy gradients |
| Adam      | Default choice  |

---

## **8. Gradient Problems** ⭐⭐

### Vanishing Gradient

* Gradients → 0
* Fixed by ReLU, BatchNorm

### Exploding Gradient

* Gradients → very large
* Fixed by gradient clipping

---

## **9. Gradient Clipping** ⭐⭐

Limits gradient size.

Used in:

* RNNs
* LSTMs

Prevents exploding gradients.

---

## **10. Early Stopping** ⭐⭐

Stop training when:

* Validation loss increases
* Training loss decreases

Prevents overfitting.

---

## **11. Data Quality & Quantity** ⭐⭐⭐

More data = better learning
Clean data = stable learning

Garbage data → garbage model

---

## **12. Shuffling Data** ⭐⭐

Shuffling:

* Prevents learning order bias
* Improves convergence

---

## **13. Loss Function Choice** ⭐⭐

Wrong loss = wrong learning.

| Task                  | Loss                      |
| --------------------- | ------------------------- |
| Regression            | MSE                       |
| Binary classification | Binary Cross Entropy      |
| Multi-class           | Categorical Cross Entropy |

---

## **14. Hardware (Hidden Factor)**

* GPU → faster training
* TPU → large-scale models
* Low memory → smaller batch size

---

## **15. Ultra-Easy Memorization Block**

```
Learning Rate → speed
LR Decay → stability
Batch size → noise vs stability
Optimizer → direction
Regularization → generalization
```

---

## **16. One-Line Exam Answers**

* Learning rate decay improves convergence near minimum.
* Batch size affects gradient noise.
* Adam is commonly used due to adaptive learning rates.
* Regularization prevents overfitting.
* Early stopping avoids overtraining.

---

## **Final One-Line Summary**

Deep learning performance depends not only on the model but also on training factors like learning rate, decay, batch size, optimizer, and regularization.

---

