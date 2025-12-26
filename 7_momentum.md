# **Momentum (in Gradient Descent)**

---

## **1. What is Momentum? (Very Simple)**

**Momentum** is a technique that helps gradient descent move **faster and smoother** by remembering **past gradients**.

> It does not forget the past completely — it uses it to move better.

---

## **2. Why Do We Need Momentum?**

### Problem with plain Gradient Descent:

* Updates zig-zag in narrow valleys
* Slow convergence
* Gets stuck or oscillates

### Momentum fixes this by:

* Smoothing updates
* Reducing zig-zag motion
* Speeding up learning

---

## **3. Simple Intuition (Must Remember)**

Think of a **ball rolling downhill**:

* It gains speed
* Doesn’t stop suddenly
* Keeps moving in the same direction

That “speed memory” is **momentum**.

---

## **4. Formula (Very Important)**

### Step 1: Update velocity (memory of gradient)

[
v_t = \beta v_{t-1} + (1 - \beta) g_t
]

### Step 2: Update weights

[
W = W - \alpha v_t
]

Where:

* (g_t) = current gradient
* (v_t) = velocity (momentum term)
* (\beta) = momentum factor (0.9 is common)
* (\alpha) = learning rate

---

## **5. Meaning of β (Momentum Factor)**

| β value | Meaning                       |
| ------- | ----------------------------- |
| 0       | No momentum (normal GD)       |
| 0.9     | Fast and smooth (most common) |
| 0.99    | Very smooth, slow response    |

**Rule:**
Higher β → more memory → smoother updates

---

## **6. Numerical Example (Very Simple)**

Assume:

* β = 0.9
* Learning rate = 0.1
* Previous velocity (v_0 = 0)
* Gradient (g_1 = 10)

Step 1:
[
v_1 = 0.9×0 + 0.1×10 = 1
]

Step 2:
[
W = W - 0.1×1 = W - 0.1
]

Next step with gradient = 8:
[
v_2 = 0.9×1 + 0.1×8 = 1.7
]

Notice:

* Updates grow smoothly
* No sudden jumps

---

## **7. Why Momentum Works (Conceptually)**

* Keeps moving in consistent direction
* Cancels out noise
* Speeds up convergence in deep networks

---

## **8. Momentum vs Normal Gradient Descent**

| Feature   | Normal GD | Momentum |
| --------- | --------- | -------- |
| Speed     | Slow      | Faster   |
| Zig-zag   | High      | Low      |
| Memory    | No        | Yes      |
| Stability | Low       | High     |

---

## **9. Where Is Momentum Used?**

* SGD with Momentum
* Adam (uses momentum internally)
* RMSProp (combined with momentum)
* Almost all deep learning optimizers

---

## **10. Interesting Facts**

* Momentum is an application of **Exponentially Weighted Moving Average**
* Introduced to fix slow learning in deep networks
* Adam optimizer = Momentum + RMSProp
* Works very well in **deep CNNs**

---

## **11. One-Line Exam Answers**

* Momentum accelerates gradient descent by adding memory of past gradients.
* It reduces oscillations and speeds up convergence.
* β controls how much past gradients influence current updates.

---

## **12. Ultra-Easy Memory Trick**

```
Gradient = direction
Momentum = speed + direction
β = memory strength
```

---

## **13. Final One-Line Summary**

Momentum improves gradient descent by remembering past gradients, making learning faster, smoother, and more stable.

