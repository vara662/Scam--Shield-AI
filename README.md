# ScamShield AI

## AI-Powered Scam Message Investigation System

ScamShield AI is a Python-based web application that analyses messages to identify potential scam indicators. It uses a locally running Gemma 3:1B model through Ollama to classify message risk, explain suspicious signs, and suggest safety precautions.

The application provides a Streamlit dashboard with interactive charts, analysis history, and downloadable investigation reports.

## Project Overview

Online scams can involve fake bank alerts, phishing messages, fraudulent job offers, lottery claims, and requests for sensitive information.

ScamShield AI helps users examine suspicious messages and understand possible warning signs before taking action.

The application is designed as an educational project. Its AI-generated results are not a guarantee that a message is safe or fraudulent.

## Features

### 1. AI Message Analysis
- Analyses SMS messages, WhatsApp messages, emails, bank alerts, and job offers.
- Uses the Gemma 3:1B model through Ollama.
- Supports English and may analyse Tamil messages, depending on model performance.

### 2. Risk Classification
Classifies messages into three risk levels:

- High Risk
- Medium Risk
- Low Risk

### 3. Risk Score
Displays an illustrative risk score from 0 to 100 based on the AI's risk classification.

The score is a simple display value, not a calibrated probability of fraud.

### 4. Warning Sign Detection
Identifies potential warning signs, such as:
- Requests for OTPs, PINs, and passwords.
- Unexpected payment requests.
- Urgent threats and pressure tactics.
- Suspicious links.
- Unexpected lottery prizes.
- Unusual job offers and registration fees.
- Requests for sensitive personal information.

### 5. Safety Recommendations
Provides practical suggestions for responding to suspicious messages.

### 6. Interactive Analytics Dashboard
Uses Plotly to display:
- Total messages analysed.
- High-risk message count.
- Medium-risk message count.
- Low-risk message count.
- Interactive bar chart.
- Interactive pie chart.
- Previous analysis records from the current session.

### 7. Analysis History
Stores completed analysis results in the current Streamlit session.

The history is not permanently stored in a database and may reset when the session restarts.

### 8. Report Download
Allows users to download:
- Individual investigation reports in JSON format.
- Analysis history in JSON format.

### 9. Modern User Interface
- Dark blue and purple theme.
- Streamlit dashboard.
- Sidebar navigation.
- Message investigation page.
- Analytics dashboard.
- Project information page.

### 10. Local AI Processing
Uses a locally running Ollama service to process messages.

No external AI API key is required for the configured local model. However, local processing does not automatically guarantee privacy in every computer or network environment.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Application logic |
| Streamlit | Web application and dashboard |
| Ollama | Local AI model runtime |
| Gemma 3:1B | Message analysis |
| Requests | Communication with the Ollama API |
| Pandas | Analysis history and data handling |
| Plotly | Interactive charts and analytics |
| JSON | Structured AI responses and report downloads |

## Project Structure

```text
ScamShield-AI/
|
|-- app.py
|-- requirements.txt
|-- README.md
```

## System Requirements

- Windows, Linux, or macOS.
- Python installed.
- Visual Studio Code or another Python editor.
- Ollama installed.
- Internet access to download the model and Python packages initially.

After downloading the model, the application can use the local model without sending prompts to a remote AI API through this application.

## Installation and Setup

### Step 1: Clone the Repository

If your project is already on your computer, open its folder in VS Code and skip this step.

Otherwise, clone your GitHub repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Move into the project folder:

```bash
cd ScamShield-AI
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your actual repository address.

### Step 2: Install Python Dependencies

Make sure `requirements.txt` contains:

```text
streamlit
requests
pandas
plotly
```

Install the dependencies:

```bash
python -m pip install -r requirements.txt
```

### Step 3: Install Ollama

Download and install Ollama from its official website:

https://ollama.com/

### Step 4: Download the AI Model

Open the terminal and run:

```bash
ollama pull gemma3:1b
```

This downloads the Gemma 3:1B model to your computer.

### Step 5: Verify the Model

Run:

```bash
ollama list
```

Confirm that `gemma3:1b` appears in the list.

### Step 6: Start the Application

Open the VS Code terminal in the project directory and run:

```bash
python -m streamlit run app.py
```

Streamlit will provide a local address, usually:

```text
http://localhost:8501
```

Open that address in your browser.

Keep Ollama available while using the application.

## How to Use

1. Launch ScamShield AI.
2. Open the Message Investigation page.
3. Select the message type.
4. Paste the message you want to investigate.
5. Click **Analyse Message**.
6. Review the risk classification and score.
7. Read the summary and warning signs.
8. Review the recommended safety actions.
9. Download the investigation report if needed.
10. Open the Analytics Dashboard to view charts and previous analyses.

## Example Test Messages

### Example 1: Suspicious Bank Message

```text
URGENT! Your bank account will be blocked today.
Send your ATM PIN and OTP immediately to verify your account.
```

Expected result: High Risk.

Reason: The message requests sensitive banking information and uses urgency.

### Example 2: Suspicious Job Offer

```text
You have been selected for a work-from-home job.
Pay a registration fee to confirm your position.
```

Expected result: Medium or High Risk.

Reason: The message requests an upfront payment.

### Example 3: Normal College Announcement

```text
Our college is organizing a technical workshop this Friday
at 10:00 AM in the seminar hall.
Interested students can register with their class coordinator.
```

Expected result: Low Risk.

Reason: The message resembles an ordinary college announcement.

These are illustrative examples. Actual classifications may differ because AI models can make mistakes.

## Risk Classification

| Risk Level | Meaning | Suggested Action |
|---|---|---|
| High | Strong indicators of potentially harmful or fraudulent activity | Stop and verify independently before acting |
| Medium | Some suspicious or uncertain indicators | Check the sender and claims carefully |
| Low | No obvious scam indicators identified | Remain cautious and verify important requests |

A low-risk classification does not establish that a message is genuine.

## Analytics Dashboard

The dashboard uses Plotly to visualise completed analyses.

### Bar Chart
Compares the number of messages classified as High, Medium, and Low Risk.

### Pie Chart
Displays the proportion of analysed messages in each risk category.

### Metrics
Shows the total number of analysed messages and the count for each risk level.

Charts update as new analyses are completed during the current session.

## Privacy and Security

- The application communicates with the configured local Ollama API.
- The default implementation does not include a remote AI API service or a permanent database.
- Analysis history is stored in Streamlit session state.
- Downloaded JSON reports may contain message text and investigation results.
- Avoid testing with real passwords, OTPs, banking credentials, or other sensitive personal information.

Local processing does not guarantee complete privacy if other software, extensions, or network configurations are involved.

## Limitations

- AI classifications may be inaccurate.
- The risk score is illustrative rather than a verified fraud probability.
- The application does not independently verify phone numbers, sender identities, websites, or financial accounts.
- The model may misunderstand Tamil or other languages.
- Suspicious links are not independently checked against threat-intelligence databases.
- Analysis history is not permanently saved.
- A message classified as Low Risk may still be fraudulent.

Always verify suspicious requests through an independent, trusted channel.

## Future Enhancements

Possible future improvements include:

- Permanent analysis history using SQLite.
- More advanced Tamil-language support.
- URL reputation checking using a trusted security service.
- Image and screenshot analysis.
- Email header analysis.
- Improved risk scoring and evaluation against labelled test messages.
- Exporting reports as PDF.
- User feedback and model performance evaluation.
- Additional language support.

## Project Objective

The objective of ScamShield AI is to demonstrate how a local language model can be integrated with Python and Streamlit to investigate suspicious messages and present the results through an interactive dashboard.

## Conclusion

ScamShield AI combines local AI inference, message risk classification, warning sign detection, safety recommendations, interactive Plotly charts, and downloadable reports in a single application.

It demonstrates the practical use of Python, Streamlit, Ollama, Gemma 3:1B, Pandas, and Plotly in an educational cybersecurity project.

## License

This project is intended for educational and demonstration purposes. Add a specific open-source license if you intend to publish and distribute the project under one.
