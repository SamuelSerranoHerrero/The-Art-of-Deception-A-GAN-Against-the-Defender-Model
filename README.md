# 🛡️ The Art of Deception: A GAN Against the Defender Model

A generative adversarial network (GAN) designed to produce malicious network traffic capable of bypassing a binary intrusion detection model — with the ultimate goal of reinforcing it through adversarial retraining.

This project was developed as the **final assignment** for the **Artificial Intelligence program** by **Samsung Innovation Campus and EOI (Escuela de Organización Industrial)**. It explores the use of **Generative Adversarial Networks (GANs)** to generate synthetic data that challenges a network-based intrusion detection system (IDS), enabling its later improvement through adversarially guided retraining.


---

## 🧠 Project Goal

The main objective is to use a **GAN to generate malicious samples that appear benign** to a previously trained binary classifier. This simulates the behavior of attackers trying to bypass detection, allowing us to:

- Identify weaknesses in the original detection model.
- Reinforce it through **retraining with adversarial synthetic data**.
- Explore the potential of GANs as a defensive tool in cybersecurity.

---

## 🔬 Technical Overview

The project is structured into several stages:

### 1. **Initial Classifier Training**
- Binary model: Benign vs Malicious.
- Trained on the `NF-UQ-NIDS-V2_Sample-2.csv` dataset.
- High accuracy (~99%) before introducing synthetic samples.

### 2. **GAN Implementation**
- **Generator**: Dense neural network that takes random vectors as input and produces synthetic network traffic.
- **Discriminator**: Replaced by the frozen binary classifier.
- **Loss function**: Measures how well the generator fools the classifier.
- Custom training loop with early stopping.

### 3. **Evaluation**
- Assessment of how often the classifier mislabels malicious samples as benign.
- Impact analysis on classifier metrics.

### 4. **Reinforcement Phase**
- Generated samples are added to the original dataset.
- The classifier is retrained to improve robustness against adversarial patterns.

---

## 🧾 Repository Structure

- `Classsifier_model.ipynb`: Dataset loading and preprocessing with the Initial binary classifier training.
- `gan_model.ipynb`: Custom GAN training loop.
- `model_comparison.py`: Comparison of models: the initial classifier and the retrained classifier.
- `graphs_demo.py`: Visual representation of the performance of both models.
- `README.md`: This file.
- `README.es.md`: Spanish version of the README.

---

## 🧪 Results

- The generator successfully creates malicious traffic misclassified as benign.
- The original model's accuracy drops under adversarial input.
- Retraining with generated samples improves classifier robustness.

---

## 📚 Conclusions

This project demonstrates the potential of generative AI not only to simulate realistic attacks but also as a **defensive strategy**. By retraining on adversarial examples, we can build more **resilient intrusion detection systems**.

---

## 🤖 Technologies Used

- Python
- Pandas, NumPy
- TensorFlow / Keras
- Scikit-learn
- Matplotlib / Seaborn

---

## 📌 Notes

This project was developed as the final work for the **Artificial Intelligence course by Samsung and EOI**, applying concepts of deep learning, generative models, and cybersecurity.

