# voice_commend-light# 🏡 Smart Home Voice Control Assistant (Google Colab Edition)

An interactive, machine learning-driven voice assistant designed to control smart home appliances (like a fan and a light) directly from your browser using **Google Colab**. This project combines natural language text classification (`scikit-learn`), browser-based microphone recording (`JavaScript`), and speech-to-text translation (`SpeechRecognition`).

---

## 🚀 Features

* **Browser Audio Capture:** Utilizes custom JavaScript to record audio straight from your browser's microphone inside Google Colab.
* **Speech-to-Text Processing:** Converts recorded voice clips into text using Google's Speech Recognition API.
* **Intent Recognition:** Uses a trained machine learning pipeline (`TfidfVectorizer` + `MultinomialNB`) to classify spoken commands.
* **Dynamic Appliance Control:** Instantly updates and displays the simulated states of home appliances (`Fan` and `Light`).

---

## 🛠️ Prerequisites & Dependencies

To run this notebook, you will need the following Python libraries installed:

```bash
pip install -q scikit-learn SpeechRecognition pydub
Code Architecture
ML Training Model:

Uses scikit-learn's Pipeline with TfidfVectorizer and MultinomialNB (Multinomial Naive Bayes) to map text inputs (e.g., "turn on fan") to specific control labels (fan_on, light_off, all_on, etc.).

Audio Recorder (record_voice):

Injects asynchronous JavaScript into the Colab output cell to capture a 5-second window from your microphone, converts it to a base64 buffer, and prepares it as a standard 16kHz WAV audio file.

Appliance Logic (control_appliances):

Parses recognized voice strings, matches keywords (handling global commands like "turn on everything" as well as individual controls), and updates device statuses.

💻 How to Run
Open a new notebook in Google Colab.

Copy and paste the script code into a code cell.

Run the cell to install dependencies and train the ML classifier.

Execute the assistant runner function in a separate cell to start listening:

Python
run_voice_command()
When prompted by the browser, allow microphone access, and speak your command within 5 seconds (e.g., "Turn on the fan" or "Switch off everything").
