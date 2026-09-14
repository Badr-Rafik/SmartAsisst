# SmartAssist

SmartAssist is a beginner-friendly AI assistant built with Python and Streamlit. It combines AI chat, task management, reminders, file processing, and downloadable document generation in one simple application.

## Features

- Chat with an AI model through OpenRouter
- Multiple saved conversations
- Create, switch, and delete chats
- Add, rename, complete, and delete tasks
- Set and edit reminder dates and AM/PM times
- Update tasks and reminders using natural language
- Browser sound alerts for due reminders while the app is open
- Upload and ask questions about:
  - PDF files
  - Word `.docx` files
  - Text `.txt` files
  - Markdown `.md` files
  - PNG, JPG, JPEG, and WEBP images
- Extract PDF text page by page
- Read Word paragraphs and tables
- Generate downloadable Word `.docx` files
- Generate downloadable PDF files
- Save chats and tasks locally in `smartassist_data.json`

## Technologies

- Python
- Streamlit
- OpenRouter API
- `nvidia/nemotron-3.5-lightning:free` for text requests
- `requests`
- `pypdf`
- `python-docx`
- `reportlab`

## Project Structure

```text
TechMaster Final Project/
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
└── smartassist_data.json   # Created automatically; ignored by Git
```

## Requirements

- Python 3.10 or newer
- An OpenRouter API key
- Internet access for AI requests

## Installation

Clone the repository and open its folder:

```powershell
git clone YOUR_GITHUB_REPOSITORY_URL
cd "TechMaster Final Project"
```

Create and activate a virtual environment:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Install the dependencies:

```powershell
pip install -r requirements.txt
```

## API Key Setup

Open `app.py` and replace the placeholder value:

```python
OPENROUTER_API_KEY = "paste-your-openrouter-api-key-here"
```

Use your own key from [OpenRouter](https://openrouter.ai/keys).

Never commit a real API key to GitHub. If a key has already been exposed, revoke it immediately and create a new one. For a public repository, a secrets manager or deployment platform secret is safer than storing a key in source code.

## Run the Application

From the project folder, run:

```powershell
streamlit run app.py
```

Open the local URL shown by Streamlit, usually:

```text
http://localhost:8501
```

## Example Chat Commands

Create a task:

```text
Add Draft project outline to my to-do list for tomorrow morning.
```

Create a reminder:

```text
Remind me to call Sarah at 8:55 PM.
```

Update a reminder:

```text
Update the reminder for my meeting with Sarah to 9:00 PM.
```

Create a Word file:

```text
Create a Word file for this task: prepare the project presentation.
```

Create a PDF file:

```text
Generate a PDF report about the project.
```

For file questions, attach a PDF, Word, text, Markdown, or image file and then ask a question in the normal chat box, such as:

```text
Summarize the main points and tell me what I should do next.
```

## How Data Is Stored

SmartAssist stores chats and tasks in `smartassist_data.json` beside `app.py`. This is a local JSON file, not a database. The file is ignored by Git so personal conversations and tasks are not uploaded accidentally.

## Reminder Limitation

Reminder alerts work while the Streamlit application and browser page are open. The app does not send phone, email, or desktop notifications when the browser is closed.

## OpenRouter Limitations

The configured free model can be busy, rate-limited, or temporarily unavailable. If a request times out, try again later. Large documents may also exceed the model's context limits.

## Security Notes

- Do not commit API keys.
- Do not share `smartassist_data.json` if it contains private conversations or tasks.
- Revoke any key that was accidentally published.
- Review uploaded files before sending them to an external AI service.
- Keep personal or confidential documents out of public repositories.

## License

Add a license before publishing the repository if you want others to reuse the project. MIT is a common choice for small open-source projects.
