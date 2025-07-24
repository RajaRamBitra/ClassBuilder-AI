# ClassBuilder AI Discord Bot

ClassBuilder AI is a powerful, multi-functional Discord bot designed to be the ultimate study assistant. Powered by the high-speed Groq API and the Llama 3 model, this bot transforms raw text and documents into structured study materials, answers questions with conversational context, and helps manage your Discord channels.

## ✨ Features

ClassBuilder AI offers a suite of features accessible through intuitive slash commands and direct mentions:

### 📚 Interactive Study Tools

- **`/summary [attachment] [word_count]`**: Generates a concise summary of uploaded text or PDF files to a specified word count.
- **`/notes [attachment]`**: Creates clean, well-structured, pointwise notes from your study materials, perfect for quick reviews.
- **`/quiz [attachment] [num_questions]`**: Generates a custom number of quiz questions based on the educational content of your documents, complete with spoiler-tagged answers. The AI is specifically instructed to ignore metadata and focus only on the core subject matter.

### 🧠 Conversational Q&A with Memory

- **`@ClassBuilder what is...?`**: Mention the bot to ask any general knowledge question or follow-up questions. The bot remembers the last 10 messages in the channel to provide contextually aware answers.

### 👋 Greetings and Help

- **`hi`, `hello`, `hey`**: The bot will respond with a friendly greeting and a list of its available commands.

### 📦 Content Export

- **`/export [format] [attachment]`**: Bundles a summary, notes, and a quiz into a single downloadable file. Supported formats are `.txt` and `.json`.

### 🛠️ Channel Moderation

- **`/clear [amount]`**: Deletes a specified number of recent messages in a channel (messages must be less than 14 days old). Requires "Manage Messages" permission.

> **Note**: This bot version does not include a `/nuke` command.

## 🚀 Setup and Installation

Follow these steps to get your own instance of the ClassBuilder AI bot running.

### 1. Prerequisites

- Python 3.8 or higher
- A Discord account and a server where you have administrative permissions

### 2. Clone the Repository

Clone this project to your local machine or open it in a cloud environment like Google Colab.

```bash
git clone <repository-url>
cd classbuilder-ai-discord-bot
```

### 3. Install Dependencies

Run the following command to install all the necessary Python libraries:

```bash
pip install -q discord.py groq python-dotenv PyMuPDF
```

This command installs:
- `discord.py` for Discord integration
- `groq` for the AI API
- `python-dotenv` for environment variable management (though `google.colab.userdata` is used in the provided notebook for secrets)
- `PyMuPDF` for PDF parsing

### 4. Configure Secret Keys

The bot requires two API keys to function. If using Google Colab, store these securely in the "Secrets" tab.

#### DISCORD_BOT_TOKEN:

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications)
2. Create a "New Application" and give it a name
3. Go to the "Bot" tab, click "Add Bot," and copy the token
4. In Google Colab, add a new secret named `DISCORD_BOT_TOKEN` and paste your token as its value

#### GROQ_API_KEY:

1. Go to [GroqCloud](https://groq.com) and sign up for a free account
2. Create a new API key and copy it
3. In Google Colab, add a new secret named `GROQ_API_KEY` and paste your API key as its value

The bot will attempt to load these secrets using `google.colab.userdata`.

### 5. Invite the Bot to Your Server

You must invite the bot using a correctly configured URL to enable slash commands.

1. In the Discord Developer Portal, go to **OAuth2 → URL Generator**
2. In the "SCOPES" box, check `bot` and `applications.commands`
3. In the "BOT PERMISSIONS" box that appears, grant the following permissions:
   - Send Messages
   - Read Message History
   - Embed Links
   - Attach Files
   - Manage Messages (for `/clear`)
4. Copy the Generated URL and paste it into your browser to invite the bot to your server

### 6. Run the Bot

Execute the Python script. If you are using the provided Colab notebook, simply run all the cells in order. The bot will start if the `DISCORD_BOT_TOKEN` and `GROQ_API_KEY` are successfully loaded.

## 📖 Usage Guide

Once the bot is online, you can interact with it in the following ways:

### Study Commands

Type `/` in a channel to see the list of commands. Select one, fill in the required options (like attaching a file or specifying a number), and press Enter.

**Example:**
```
/summary attachment: [upload your PDF] word_count: 150
```

### General Questions

Mention the bot directly in your message.

**Example:**
```
@ClassBuilder what are the main types of machine learning?
```

### Follow-up Questions

After the bot responds, mention it again with a follow-up.

**Example:**
```
@ClassBuilder can you explain the first one in more detail?
```

## 💻 Technologies Used

- **Backend**: Python
- **API**: Groq with the `llama3-70b-8192` model
- **Discord Integration**: `discord.py`
- **PDF Parsing**: `PyMuPDF`

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the [MIT License](LICENSE).
