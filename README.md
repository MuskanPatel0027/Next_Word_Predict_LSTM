# 🔮 Next Word Prediction using LSTM

A Deep Learning-based **Next Word Prediction** application that uses **Recurrent Neural Networks (RNN)** and **Long Short-Term Memory (LSTM)** to predict the next word based on the context provided by the user.

The project includes a trained LSTM model, tokenizer, sequence-length configuration, and an interactive application for generating next-word predictions.

## 🚀 Project Demo

🔗 **GitHub Repository:**
https://github.com/MuskanPatel0027/Next_Word_Predict_LSTM

🔗 **Live Application:**
https://next-step-prediction.streamlit.app/

---

## 📌 Overview

Next Word Prediction is a fundamental **Natural Language Processing (NLP)** task used in applications such as:

* ✍️ Smart text completion
* ⌨️ Predictive keyboards
* 💬 Chatbots
* 📧 Email autocomplete
* 🔎 Search suggestions
* 📝 Text generation

In this project, an LSTM-based neural network learns patterns and relationships between words from a text corpus. Given a sequence of words, the model predicts the most likely next word.

### Example

```text
Input:
"Life is"

Prediction:
"beautiful"
```

The model uses the previously entered words as context and predicts the next word based on patterns learned during training.

---

# 🧠 How It Works

The complete pipeline can be represented as:

```text
             Input Text
                  │
                  ▼
        ┌──────────────────┐
        │ Text Preprocessing│
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │    Tokenization  │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │ Sequence Padding │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │   LSTM / RNN     │
        │      Model       │
        └────────┬─────────┘
                 │
                 ▼
        ┌──────────────────┐
        │ Next Word        │
        │ Prediction       │
        └──────────────────┘
```

---

# 🏗️ Model Architecture

The project uses a recurrent neural network architecture with an **LSTM layer** for sequence learning.

```text
Input Text
    ↓
Tokenization
    ↓
Integer Sequences
    ↓
Padding
    ↓
Embedding
    ↓
LSTM
    ↓
Dense Layer
    ↓
Probability Distribution
    ↓
Predicted Next Word
```

### Why LSTM?

Traditional RNNs can struggle with long-term dependencies because of the vanishing-gradient problem.

**LSTM (Long Short-Term Memory)** networks use memory cells and gates to retain important information over longer sequences.

This makes LSTM particularly useful for NLP and language modeling tasks.

---

# 🔄 Prediction Process

When the user enters a sentence:

### 1. Tokenization

The input sentence is converted into numerical tokens using the trained tokenizer.

```text
"I love machine"
        ↓
[12, 45, 87]
```

### 2. Sequence Preparation

The token sequence is padded to match the input length expected by the trained model.

### 3. Model Prediction

The padded sequence is passed to the trained LSTM model.

The model produces probabilities for the words in its vocabulary.

### 4. Next Word Selection

The word corresponding to the highest predicted probability is selected as the next word.

```text
Input:
"I love machine"

          ↓

LSTM Model

          ↓

Predicted:
"learning"
```

---

# 🛠️ Tech Stack

| Technology               | Purpose                               |
| ------------------------ | ------------------------------------- |
| Python                   | Programming language                  |
| TensorFlow / Keras       | Deep Learning                         |
| LSTM                     | Sequence modeling                     |
| RNN                      | Recurrent neural network architecture |
| NLP                      | Natural Language Processing           |
| NumPy                    | Numerical operations                  |
| Pandas                   | Data processing                       |
| Streamlit                | Interactive web application           |
| Jupyter Notebook         | Model development                     |
| Git & GitHub             | Version control                       |
| Render / Streamlit Cloud | Deployment                            |

---

# 📂 Project Structure

```text
Next_Word_Predict_LSTM/
│
├── .vscode/
│   └── VS Code configuration
│
├── app.py
│   └── Streamlit application and prediction logic
│
├── lstm_model.h5
│   └── Trained LSTM model
│
├── tokenizer.pkl
│   └── Saved tokenizer used for text preprocessing
│
├── max_len.pkl
│   └── Maximum sequence length used by the model
│
├── next_text_predict_LSTM_RNN.ipynb
│   └── Model training and experimentation notebook
│
├── qoute_dataset.csv
│   └── Dataset used for training
│
├── requirements.txt
│   └── Python dependencies
│
├── runtime.txt
│   └── Runtime configuration for deployment
│
└── README.md
    └── Project documentation
```

The repository currently contains these model and application artifacts directly in the project structure.

---

# ⚙️ Installation

## 1. Clone the repository

```bash
git clone https://github.com/MuskanPatel0027/Next_Word_Predict_LSTM.git
```

Navigate into the project:

```bash
cd Next_Word_Predict_LSTM
```

---

## 2. Create a virtual environment

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### macOS / Linux

```bash
source venv/bin/activate
```

---

## 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will open in your browser at:

```text
http://localhost:8501
```

---

# 💻 Using the Application

1. Open the Streamlit application.
2. Enter a sentence or phrase.
3. Submit the text.
4. The trained LSTM model processes the input.
5. The application predicts the next word.

### Example

```text
Input:
"The future of artificial"

Output:
"intelligence"
```

The exact prediction depends on the vocabulary and patterns learned from the training dataset.

---

# 📊 Model Training

The model was developed and experimented with using:

```text
next_text_predict_LSTM_RNN.ipynb
```

The notebook contains the workflow for:

* Dataset loading
* Text preprocessing
* Tokenization
* Sequence generation
* Padding
* Model creation
* LSTM training
* Model evaluation
* Prediction testing
* Model and tokenizer saving

---

# 🧹 Text Preprocessing

The NLP preprocessing pipeline converts raw text into a format suitable for the neural network.

General workflow:

```text
Raw Text
   ↓
Text Cleaning
   ↓
Tokenization
   ↓
Generate Sequences
   ↓
Padding
   ↓
Model Input
```

The tokenizer is saved as:

```text
tokenizer.pkl
```

This allows the application to use the **same vocabulary and word-to-index mapping** that was used during model training.

---

# 💾 Saved Model Artifacts

The repository contains the required artifacts for inference:

### `lstm_model.h5`

Contains the trained LSTM neural network.

### `tokenizer.pkl`

Stores the tokenizer and vocabulary mapping used to convert text into numerical sequences.

### `max_len.pkl`

Stores the maximum sequence length required during prediction.

Keeping these artifacts consistent with the training pipeline is important because the model expects the same preprocessing configuration during inference.

---

# 🌐 Deployment

The project is designed to run as an interactive web application using Streamlit.

### Live Application

**Next Word Prediction:**
https://next-step-prediction.streamlit.app/

Users can enter text directly into the application and receive a predicted next word without running the model locally.

---

# ✨ Features

* ✅ NLP-based text processing
* ✅ RNN-based sequence modeling
* ✅ LSTM neural network
* ✅ Next-word prediction
* ✅ Saved trained model
* ✅ Saved tokenizer
* ✅ Sequence padding
* ✅ Interactive Streamlit interface
* ✅ Deployment-ready project
* ✅ Jupyter notebook for experimentation

---

# 🎯 Applications

This type of model can be used as a foundation for:

* Smart keyboards
* Text autocomplete
* Email suggestions
* Chatbot systems
* Search autocomplete
* Content generation
* Writing assistants
* NLP research projects

---

# 📚 Concepts Demonstrated

This project demonstrates practical understanding of:

### Deep Learning

* Recurrent Neural Networks
* LSTM
* Embedding layers
* Dense layers
* Softmax probability prediction

### NLP

* Text preprocessing
* Tokenization
* Sequence generation
* Padding
* Language modeling
* Next-word prediction

### Deployment

* Model serialization
* Streamlit
* Application deployment
* Dependency management

---

# 💼 Resume Description

### Next Word Prediction using LSTM

> Developed an NLP-based next-word prediction system using RNN and LSTM architectures. Implemented text tokenization, sequence generation, padding, and deep learning-based language modeling, then deployed the trained model through an interactive Streamlit application for real-time next-word prediction.

### Technologies

**Python, NLP, TensorFlow/Keras, RNN, LSTM, NumPy, Pandas, Streamlit**

---

# 👩‍💻 Author

**Muskan Patel**

GitHub:
https://github.com/MuskanPatel0027

Project:
https://github.com/MuskanPatel0027/Next_Word_Predict_LSTM

---

# ⭐ Support

If you found this project useful, consider giving the repository a ⭐ on GitHub.
