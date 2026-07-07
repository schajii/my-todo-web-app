# My Todo Web App

A simple browser-based todo app built with [Streamlit](https://streamlit.io/). Add items, check them off to complete, and your list persists in a plain text file.

**Live app:** [my-todo-web-app-test.streamlit.app](https://my-todo-web-app-test.streamlit.app)

## Features

- Add todos from a text input
- Mark todos complete with checkboxes
- Todos saved to `todos.txt` and persist between sessions
- Shared read/write helpers in `functions.py`

## Requirements

- Python 3.12+
- Streamlit

## Local Setup

Clone the repository and install dependencies with [uv](https://github.com/astral-sh/uv):

```bash
git clone https://github.com/schajii/my-todo-web-app.git
cd my-todo-web-app
uv sync
```

Or install with pip:

```bash
pip install -r requirements.txt
```

## Run Locally

```bash
uv run streamlit run web.py
```

Streamlit opens the app in your browser, usually at `http://localhost:8501`.

## Usage

1. Type a new todo in the input box at the bottom and press Enter to add it.
2. Check a todo's checkbox to mark it complete and remove it from the list.

## Deployment

This project includes a `requirements.txt` for hosting platforms that expect a pip-style dependency file.

Generate an updated `requirements.txt` after adding packages:

```bash
uv pip freeze > requirements.txt
```

### Streamlit Community Cloud

The app is deployed at [my-todo-web-app-test.streamlit.app](https://my-todo-web-app-test.streamlit.app).

To deploy or redeploy:

1. Push this repository to GitHub.
2. Go to [share.streamlit.io](https://share.streamlit.io) and connect your repo.
3. Set the main file path to `web.py`.
4. Deploy.

> **Note:** On cloud hosting, `todos.txt` is stored on the server filesystem and may reset when the app is redeployed or restarted.

## Project Structure

```text
todo_webapp/
├── web.py              # Streamlit entry point
├── functions.py        # Read/write helpers
├── todos.txt           # Todo storage (created automatically)
├── requirements.txt    # Pinned dependencies for deployment
├── pyproject.toml
├── uv.lock
└── README.md
```

## Data Storage

Todos are saved to `todos.txt` in the project directory. The file is created automatically on first run if it does not exist.
