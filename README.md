## **1. Artificial Neural Network (ANN)**

**Layman definition:**
A simple ANN is like a small “brain” made of mathematical neurons. It learns patterns by adjusting connections between them.

**Real-life use case:**
Predicting house prices, classifying emails as spam or not, predicting exam marks from past data.

**Subparts:**

* **Input layer** – where data enters
* **Hidden layers** – where learning happens
* **Output layer** – final prediction
* **Weights & Biases** – adjustable knobs the network learns
* **Activation functions** – help the network learn complex patterns

---

## **2. Convolutional Neural Network (CNN)**

**Layman definition:**
A CNN is a special neural network that can “see” images. It focuses on edges, shapes, and textures like the human eye.

**Real-life use case:**
Face recognition, medical image detection (tumors), identifying objects in photos.

**Subparts:**

* **Convolution layer** – detects features (edges, colors)
* **Pooling layer** – compresses image information
* **Fully connected layer** – final prediction
* **Feature maps** – extracted meaningful patterns

---

## **3. Recurrent Neural Network (RNN)**

**Layman definition:**
An RNN remembers previous information. It is used for data that comes in a sequence (past affects the future).

**Real-life use case:**
Predicting next word while typing, stock price forecasting, language translation.

**Subparts:**

* **Recurrent cell** – keeps memory
* **Hidden state** – stores previous information
* **LSTM** – advanced RNN with better long-term memory
* **GRU** – simplified LSTM

---

## **4. Generative Adversarial Network (GAN)**

**Layman definition:**
GANs are two neural networks fighting each other — one creates fake data, the other checks if it’s real.
This makes GANs good at generating realistic images.

**Real-life use case:**
Creating fake human faces, image-to-image conversion (day → night), restoring old photos.

**Subparts:**

* **Generator** – creates fake images
* **Discriminator** – checks if image is real or fake
* **Training loop** – both compete and improve

---

## **5. Autoencoders**

**Layman definition:**
An autoencoder learns to compress data and rebuild it again. Like zipping and unzipping a file.

**Real-life use case:**
Removing noise from images, compressing photos, reducing data for ML models.

**Subparts:**

* **Encoder** – compresses data into a small form
* **Latent space** – the compressed representation
* **Decoder** – reconstructs original data

---

## **6. Auto-Decoders**

**Layman definition:**
Unlike autoencoders, auto-decoders don't have an encoder. They only have a decoder that learns to reconstruct data directly from a learned embedding. Mostly used for 3D data.

**Real-life use case:**
3D shape reconstruction, neural radiance fields (NeRFs).

**Subparts:**

* **Latent code** – learned directly
* **Decoder network** – reconstructs final output

---

## **7. Transformers**

**Layman definition:**
Transformers are models that understand relationships between words or tokens at once (not step-by-step), making them fast and highly accurate.

They are the reason why ChatGPT exists.

**Real-life use case:**
ChatGPT, BERT, summarizing documents, translation, speech recognition.

**Subparts:**

* **Self-attention** – tells the model which words matter
* **Feed-forward layers** – process the information
* **Positional encoding** – tells the model the order of words
* **Encoder** – understands input
* **Decoder** – generates output

---

## **8. Object Detection**

**Layman definition:**
Object detection tells **what** objects are in an image **and where** they are by placing bounding boxes.

**Real-life use case:**
Self-driving cars identifying pedestrians, detecting helmets in CCTV.

**Subparts:**

* **Backbone** – feature extractor
* **Region proposal / anchor boxes** – guess where objects might be
* **Classifier** – names the object
* **Bounding box regressor** – draws the box
  Models like:
* **YOLO**
* **SSD**
* **Faster R-CNN**

---

## **9. Image Segmentation**

**Layman definition:**
Segmentation paints each pixel of an image with a label. It not only finds the object but identifies its exact shape.

**Real-life use case:**
Medical scans (detect tumor boundary), background removal in photos.

**Subparts:**

* **Semantic segmentation** – classify every pixel
* **Instance segmentation** – classify and separate each object instance
* **Key architectures:**

  * **UNet**
  * **Mask R-CNN**

---
