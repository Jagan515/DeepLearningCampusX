# **RMSProp (Root Mean Square Propagation)**

---

## **1. What is RMSProp? (Very Simple)**

**RMSProp** is an optimizer that **fixes the main problem of AdaGrad**.

> It adapts the learning rate **but does NOT let it go to zero**.

---

## **2. Why Was RMSProp Introdued?**

### Problem with AdaGrad:

* Keeps adding squared gradients forever
* Learning rate becomes **too small**
* Training stops early

### RMSProp solution:

* Uses **exponentially weighted moving average**
* Forgets old gradients gradually
* Learning continues smoothly

---

## **3. Core Idea (1 Line)**

> Use recent gradients more, forget old gradients.

---

## **4. How RMSProp Works (Conceptually)**

Instead of summing all squared gradients:

* RMSProp keeps a **moving average of squared gradients**
* Older gradients slowly fade away

This keeps learning rate **stable**.

---

## **5. Formula (Very Important)**

### Step 1: Update moving average of squared gradients

[
v_t = \beta v_{t-1} + (1 - \beta) g_t^2
]

### Step 2: Update parameters

[
\theta = \theta - \frac{\alpha}{\sqrt{v_t} + \epsilon} \cdot g_t
]

Where:

* (g_t) = current gradient
* (v_t) = moving average of squared gradients
* (\beta) ≈ 0.9 (decay rate)
* (\alpha) = learning rate
* (\epsilon) = small constant

---

## **6. Meaning of β (Decay Rate)**

| β value | Meaning           |
| ------- | ----------------- |
| 0.9     | Most common       |
| 0.99    | Very smooth       |
| 0.999   | Very slow updates |

Higher β → more memory → smoother learning

---

## **7. When Should We Use RMSProp?** ⭐⭐

### ✅ Use RMSProp when:

* Gradients are **noisy**
* Training **RNNs**
* Loss fluctuates a lot
* AdaGrad fails
* Dataset is non-stationary

---

## **8. When NOT to Use RMSProp** ❌

### ❌ Avoid RMSProp when:

* Adam is available (Adam is usually better)
* Need bias correction
* Want momentum + adaptive learning together

---

## **9. RMSProp vs AdaGrad vs Momentum**

| Feature         | AdaGrad | RMSProp   | Momentum |
| --------------- | ------- | --------- | -------- |
| Adaptive LR     | Yes     | Yes       | No       |
| LR decay issue  | Yes     | Fixed     | No       |
| EWMA used       | No      | Yes       | Yes      |
| Noisy gradients | Poor    | Excellent | Medium   |

---

## **10. Relationship with Other Optimizers**

* **AdaGrad** → RMSProp (fixes LR decay)
* **RMSProp + Momentum** → Adam (conceptually)
* RMSProp inspired modern optimizers

---

## **11. Interesting Facts**

* Proposed by **Geoff Hinton**
* Never officially published as a paper
* Very popular before Adam
* Works well for RNNs
* Uses EWMA just like Momentum

---

## **12. One-Line Exam Answers**

* RMSProp uses an exponentially weighted average of squared gradients.
* It prevents learning rate from becoming too small.
* RMSProp works well for noisy and non-stationary problems.
* It is an improvement over AdaGrad.

---

## **13. Ultra-Easy Memory Trick**

```
AdaGrad problem → LR → 0
RMSProp fix → forget old gradients
EWMA → stability
```

---

## **14. Final One-Line Summary**

RMSProp improves AdaGrad by using exponentially weighted averages to maintain stable learning rates during training.

---
