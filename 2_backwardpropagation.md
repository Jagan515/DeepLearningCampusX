# **1. Small MLP Example**

* Input layer: 2 neurons → (x_1 = 1, x_2 = 2)
* Hidden layer: 2 neurons → ReLU activation
* Output layer: 1 neuron → linear

**Weights and biases:**

```
W1 = [[0.1, 0.2],
      [0.3, 0.4]]   b1 = [0.1, 0.1]
W2 = [0.5, 0.6]   b2 = 0.1
```

Actual output: (y_{true} = 1)

---

# **2. Forward Propagation (Calculate Output)**

**Step 1: Hidden layer pre-activation**

[
z_{hidden} = x \cdot W1 + b1
]

Neuron 1: (z_1 = 1*0.1 + 2*0.3 + 0.1 = 0.8)
Neuron 2: (z_2 = 1*0.2 + 2*0.4 + 0.1 = 1.1)

**Step 2: Hidden layer activation (ReLU)**

[
a_{hidden} = [0.8, 1.1]  \quad (\text{ReLU leaves positive numbers as is})
]

**Step 3: Output layer**

[
z_{out} = a_{hidden} \cdot W2 + b2 = 0.8*0.5 + 1.1*0.6 + 0.1 = 1.16
]

[
y_{pred} = 1.16
]

✅ Forward pass complete.

---

# **3. Backward Propagation (Update Weights & Biases)**

**Step 1: Compute loss gradient**
[
L = \frac12 (y_{pred} - y_{true})^2 \implies \frac{dL}{dy_{pred}} = y_{pred} - y_{true} = 0.16
]

---

**Step 2: Output layer gradients**

[
\frac{dL}{dW2} = 0.16 * a_{hidden} = [0.128, 0.176]
]
[
\frac{dL}{db2} = 0.16
]

---

**Step 3: Hidden layer gradients**

[
\delta_{hidden} = \frac{dL}{dy_{pred}} * W2 = 0.16 * [0.5, 0.6] = [0.08, 0.096]
]

(ReLU derivative = 1, so delta stays the same)

[
\frac{dL}{dW1} = x^T * \delta_{hidden} = [[0.08, 0.096],[0.16, 0.192]]
]
[
\frac{dL}{db1} = [0.08, 0.096]
]

---

# **4. Step 4: Update Weights & Biases (Gradient Descent)**

Learning rate = 0.1

```
W1_new = W1 - 0.1*dL/dW1 = [[0.092,0.1904],[0.284,0.3808]]
b1_new = b1 - 0.1*dL/db1 = [0.092,0.0904]

W2_new = W2 - 0.1*dL/dW2 = [0.4872,0.5824]
b2_new = b2 - 0.1*dL/db2 = 0.084
```

✅ Now the network has **updated weights and biases**. Next forward pass will be slightly closer to the true output.

---

# **5. Key Takeaways (Clean Summary)**

1. **Forward Propagation:**

* Multiply inputs by weights, add biases, apply activation → get prediction

2. **Loss:**

* Compare prediction with true value

3. **Backward Propagation:**

* Calculate gradient of loss w.r.t weights & biases

4. **Update Parameters:**

* New weight = old weight – learning_rate * gradient
* New bias = old bias – learning_rate * gradient

5. Repeat **forward → backward → update** many times → network learns

---
