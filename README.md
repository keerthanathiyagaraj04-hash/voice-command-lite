# Voice-Controlled Smart Home Assistant (Python / Colab)

A lightweight prototype demonstrating a voice-controlled smart home automation system built in Google Colab. It uses JavaScript (`MediaRecorder`) to capture voice input directly in the browser, processes the audio using Python's Speech Recognition library, classifies the command via a scikit-learn machine learning pipeline (`TfidfVectorizer` + `MultinomialNB`), and controls virtual appliances.

## Features

- **Browser Audio Capture:** Records voice directly through the browser microphone using a JavaScript bridge in Google Colab.
- **Speech Recognition:** Converts recorded audio into text using Google's speech recognition API.
- **Intent Classification:** Uses a Naive Bayes classifier trained on various phrasing permutations to map natural language commands to specific actions.
- **Appliance Control:** Toggles simulated smart home devices (`fan` and `light`) individually or collectively (`all_on`, `all_off`).

## Prerequisites

The project requires the following Python libraries and dependencies:

```bash
Code Structure
Model Training: Initializes a pipeline with TF-IDF vectorization and a Multinomial Naive Bayes classifier, training it on command phrases like "turn on fan", "switch off light", and "turn on everything".

Audio Recording: Executes asynchronous JavaScript code via Colab to capture audio via navigator.mediaDevices.getUserMedia, returning base64-encoded bytes to Python.

Audio Conversion: Converts the captured audio stream into a 16kHz mono WAV format using pydub.

Command Execution: Matches recognized text against defined appliance rules and prints the current smart home status.

Example Usage
Run the main execution loop in your notebook:

Python
run_voice_command()
When prompted, speak a command like "turn on fan" within 5 seconds.

Sample Output
Plaintext
Speak within the next 5 seconds...
Recognized voice: turn on fan

--- SMART HOME STATUS ---
Fan: ON
Light: OFF
Recording complete.pip install -q scikit-learn SpeechRecognition pydub# voice-command-lite
