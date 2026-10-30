# ScamShield AI

## AI-Powered Scam Message Investigation

ScamShield AI is a Python-based application that uses a locally running Large Language Model (LLM) to analyze messages and identify potential scam indicators. It provides a risk assessment, highlights suspicious phrases, and recommends safety actions through an interactive Streamlit dashboard.

## Project Overview

ScamShield AI helps users examine suspicious SMS messages, emails, job offers, and payment requests. The application analyzes the message content and explains possible warning signs.

The application uses Ollama to run the Gemma 3:1B model locally, without requiring a cloud-based AI API.

## Features

- AI-powered message analysis
- Risk classification: Low Concern, Medium Concern, and High Concern
- Identification of suspicious phrases
- Explanation of potential warning signs
- Recommended digital safety actions
- Interactive dashboard with a dark blue and purple theme
- Ollama connection and model status checks
- Downloadable investigation reports in JSON format
- Local LLM integration

## Technologies Used

- Python
- Streamlit
- Ollama
- Gemma 3:1B
- Requests
- JSON

## Project Structure

```text
ScamShield-AI/
│
├── app.py
├── requirements.txt
└── README.md
```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your actual GitHub repository URL.

### 2. Open the Project Folder

Open the downloaded project folder in Visual Studio Code.

### 3. Install Python Dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Install Ollama

Download and install Ollama from its official website:

https://ollama.com/

### 5. Download the AI Model

Open your terminal and run:

```bash
ollama pull gemma3:1b
```

Wait for the download to finish.

### 6. Run the Application

Execute the following command:

```bash
python -m streamlit run app.py
```

The application will open in your browser. If it does not open automatically, visit the local address displayed in the terminal, usually `http://localhost:8501`.

## How to Use

1. Launch the ScamShield AI application.
2. Enter a message in the text area.
3. Click the **Analyze Message** button.
4. Review the risk assessment.
5. Examine the identified warning signs.
6. Read the recommended safety actions.
7. Download the investigation report as a JSON file if required.

## Risk Classification

| Risk Level | Description |
|---|---|
| Low Concern | No clear warning signs were identified in the message. |
| Medium Concern | Some potentially suspicious indicators were identified. |
| High Concern | Strong warning signs may be present. |

The risk classification is an AI-generated assessment and is not proof that a message is genuine or fraudulent.

## Example Use Cases

- Analyzing suspicious banking notifications
- Examining unexpected job offers
- Reviewing messages requesting personal information
- Identifying pressure tactics in payment requests
- Examining potentially fraudulent prize notifications

## Privacy and Security

ScamShield AI sends message content to the locally running Ollama service for analysis.

The application code does not intentionally send messages to a cloud AI API. However, users should ensure that their computer, Ollama installation, and network environment meet their privacy requirements.

Avoid sharing sensitive personal information when testing the application.

## Limitations

- AI-generated results may be inaccurate.
- The application cannot independently verify a sender's identity.
- Website authenticity is not verified automatically.
- Legitimate messages may contain suspicious-looking language.
- A low-risk result does not guarantee that a message is safe.

Always verify important requests through official channels.

## Future Improvements

- Support for multiple languages
- Message history and investigation tracking
- Improved risk scoring
- Email message analysis
- Additional local AI models
- Enhanced reporting and visualization

## Conclusion

ScamShield AI demonstrates how Large Language Models can assist with digital safety by analyzing message content and explaining potential scam indicators. By combining Python, Streamlit, Ollama, and Gemma 3:1B, the project provides an interactive interface for educational scam-awareness analysis.

## Author

Developed as an AI and Python project.

## License

This project is intended for educational and research purposes. Add an appropriate open-source license if you plan to distribute the code.
