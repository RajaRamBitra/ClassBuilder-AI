# ClassBuilder AI Discord Bot

ClassBuilder AI is a powerful, multi-functional Discord bot designed to be the ultimate study assistant. Powered by the high-speed Groq API and the Llama 3 model, this bot transforms raw text and documents into structured study materials, answers questions with conversational context, and helps manage your Discord channels.

This project upgrades a previous version that used local Hugging Face models, replacing them with a robust, fast, and intelligent API-driven backend for significantly improved performance and quality.

✨ Features
---
ClassBuilder AI offers a suite of features accessible through intuitive slash commands and direct mentions:

### 📚 Interactive Study Tools
* **/summary \[attachment] \[word_count]:** Generates a concise summary of uploaded text or PDF files to a specified word count.
* **/notes \[attachment]:** Creates clean, well-structured, pointwise notes from your study materials, perfect for quick reviews.
* **/quiz \[attachment] \[num_questions]:** Generates a custom number of quiz questions based on the educational content of your documents, complete with spoiler-tagged answers. The AI is specifically instructed to ignore metadata and focus only on the core subject matter.

### 🧠 Conversational Q&A with Memory
* **@ClassBuilder what is...?:** Mention the bot to ask any general knowledge question or follow-up questions. The bot remembers the last 10 messages in the channel to provide contextually aware answers.

### Greetings and Help
* **hi, hello, hey:** The bot will respond with a friendly greeting and a list of its available commands.

### 📦 Content Export
* **/export \[format] \[attachment]:** Bundles a summary, notes, and a quiz into a single downloadable file. Supported formats are `.txt` and `.json`.

### 🛠️ Channel Moderation
* **/clear \[amount]:** Deletes a specified number of recent messages in a channel (messages must be less than 14 days old). Requires "Manage Messages" permission.
* **/nuke:** Irreversibly clears all messages in a channel by cloning it and deleting the original. Requires "Manage Channels" permission.

---
🚀 Setup and Installation
---
Follow these steps to get your own instance of the ClassBuilder AI bot running.

### 1. Prerequisites
* Python 3.8 or higher
* A Discord account and a server where you have administrative permissions.

### 2. Clone the Repository
Clone this project to your local machine or open it in a cloud environment like Google Colab.

### 3. Install Dependencies
Run the following command to install all the necessary Python libraries:
```bash
pip install -q discord.py groq python-dotenv PyMuPDF
