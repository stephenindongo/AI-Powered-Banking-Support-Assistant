# Banking Customer Support System

This repository presents a banking customer support application designed to streamline customer interactions through conversational AI. The system combines a Streamlit-based interface with sentence-transformer models for intent classification and Gemini for context-aware response generation. It is built to assist users with common banking inquiries while improving service responsiveness and accessibility.

## Key Features

- **Speech Recognition:** Captures customer voice input and converts it into text using OpenAI Whisper for accurate transcription.
- **Intent Classification:** Maps user queries to predefined banking intents using sentence embeddings and cosine similarity.
- **Contextual Response Generation:** Uses Gemini with chat history to generate relevant, informative, and conversational responses.
- **Text-to-Speech Output:** Converts system responses into audio to support a more natural and accessible user experience.

## Installation

1. Clone the repository to your local environment.
2. Create and activate a virtual environment for dependency isolation.
3. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Add your OpenAI API key in a `.env` file:

   ```bash
   OPENAI_API_KEY="your_openai_api_key"
   ```

## Usage

1. Launch the application:

   ```bash
   streamlit run app.py
   ```

2. Interact with the system through the Streamlit interface:

- Enter a question or message in the chat input.
- Alternatively, click the microphone icon and record a voice query.

## Project Structure

- `app.py`: Main application logic for the Streamlit user interface, input handling, and orchestration of chatbot interactions.
- `chatbot.py`: Defines the `ChatBot` class responsible for intent classification and response generation using sentence-transformer models and LLM-based reasoning.
- `audio_utils.py`: Provides utilities for speech-to-text conversion, text-to-speech generation, and audio playback within the application.

## Technical Overview

### Intent Classification

The system generates sentence embeddings for both the incoming user message and the predefined banking intents. It compares the embeddings using cosine similarity to determine the most relevant intent for the query.

### Chatbot Response Generation

The `ChatBot` object integrates a language model pipeline and a custom prompt template. By leveraging chat history and contextual memory, the model generates responses aligned with the identified intent and the user’s conversation state.

### Audio Processing

OpenAI Whisper is used to transcribe spoken input into text, while the gTTS library converts the assistant’s response into an audio file. The application displays the transcript and plays the generated speech to the user.
