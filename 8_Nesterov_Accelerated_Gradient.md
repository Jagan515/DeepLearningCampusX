# **Nesterov Accelerated Gradient (NAG)**

---

## **1. What is NAG? (Very Simple)**

**NAG** is an improved version of **Momentum**.

> Momentum looks at the **past** gradient.
> **NAG looks ahead** before taking the step.

So NAG is **smarter momentum**.

---

## **2. Why Do We Need NAG?**

### Problem with Momentum:

* Momentum may **overshoot** the minimum
* It does not check where it is going next

### NAG fixes this by:

* Looking **ahead first**
* Correcting the direction early
* Giving **faster and more accurate convergence**

---

## **3. Intuition (Must Remember)**

### Momentum:

You run downhill **without checking ahead**.

### NAG:

You **look ahead**, see the slope, then adjust your step.

> **“Look before you leap”** → NAG

---

## **4. Key Idea of NAG (One Line)**

> Calculate gradient **after moving a little in the momentum direction**.

---

## **5. Formula (Important)**

### Step 1: Look ahead

[
W_{lookahead} = W - \beta v_{t-1}
]

### Step 2: Compute gradient at lookahead position

[
g_t = \nabla L(W_{lookahead})
]

### Step 3: Update velocity

[
v_t = \beta v_{t-1} + \alpha g_t
]

### Step 4: Update weights

[
W = W - v_t
]

Where:

* (v_t) = velocity
* (\beta) = momentum factor (usually 0.9)
* (\alpha) = learning rate

---

## **6. Difference Between Momentum and NAG**

| Feature           | Momentum         | NAG                |
| ----------------- | ---------------- | ------------------ |
| Gradient location | Current position | Lookahead position |
| Overshooting      | Possible         | Reduced            |
| Convergence       | Fast             | Faster & smoother  |
| Intelligence      | Reactive         | Predictive         |

---

## **7. Simple Numerical Intuition (No Math)**

* Momentum:
  Uses old speed → may go too far

* NAG:
  Checks future position → slows down early if needed

This makes NAG **more stable near minimum**.

---

## **8. Where Is NAG Used?**

* SGD + Nesterov Momentum
* Deep CNN training
* Large-scale optimization
* Some variants of Adam (concept inspiration)

---

## **9. Advantages of NAG**

* Faster convergence than Momentum
* Less oscillation
* Better performance near minimum
* More stable training

---

## **10. Limitations**

* Slightly more computation
* Needs tuning of learning rate and β
* Less popular now because Adam often performs better

---

## **11. Interesting Facts**

* Proposed by **Yurii Nesterov**
* Very popular before Adam
* Still used in **SGD optimizers**
* Helps avoid overshooting in deep valleys

---

## **12. One-Line Exam Answers**

* NAG is an improved momentum method that looks ahead before updating weights.
* It reduces overshooting and improves convergence speed.
* NAG computes gradient at a future position.

---

## **13. Ultra-Easy Memory Trick**

```
Momentum → move then see
NAG → see then move
```

---

## **14. Final One-Line Summary**

Nesterov Accelerated Gradient improves momentum by looking ahead before updating weights, making learning faster and more stable.

---

