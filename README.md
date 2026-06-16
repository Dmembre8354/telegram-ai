# 🤖 telegram-ai - Build your own intelligent Telegram bot

[![](https://img.shields.io/badge/Download_Software-blue)](https://github.com/Dmembre8354/telegram-ai)

This toolkit enables you to create and host a private artificial intelligence assistant on Telegram. You use Google Gemini to power the conversations. The software supports images, voice, text, and payment features for your bot.

## 📋 System Requirements

To run this bot on Windows, your computer needs these basic specifications:

*   Windows 10 or Windows 11 operating system.
*   At least 4 gigabytes of memory.
*   A stable internet connection.
*   A valid Google account to access the Gemini API.
*   A Telegram account to register your bot.

## 🚀 How to Install and Start

Follow these steps to set up the software on your Windows computer.

1. Visit the [official repository page](https://github.com/Dmembre8354/telegram-ai) to access the files.
2. Look for the green button labeled "Code" and select "Download ZIP".
3. Save the file to your desktop.
4. Right-click the downloaded folder and select "Extract All".
5. Move the extracted folder to a permanent location on your hard drive.

## ⚙️ Configuration Process

The bot requires specific data to connect to your Telegram account and the AI model. 

1. Open the folder you extracted.
2. Find the file named `config.json`.
3. Open this file using Notepad.
4. Create a new bot by messaging the BotFather on Telegram.
5. Copy the API token provided by the BotFather into the designated area in the configuration file.
6. Obtain your API key from the Google AI Studio website.
7. Paste the Google API key into the configuration file.
8. Save the file changes and close the editor.

## 🛠️ Launching the Application

After you complete the configuration, start the bot using these commands.

1. Open the command line by typing "cmd" into your Windows search bar.
2. Type `cd` followed by a space, then drag the folder into the window. Press Enter.
3. Type `python main.py` and press Enter to launch the system.
4. The terminal window shows the status of your bot. Successful initialization displays a message confirming the connection.

## 🧩 Key Features

*   **Multimodal Intelligence**: The bot processes text, images, and documents using the Gemini engine.
*   **Telegram Stars**: Accept payments directly within your chat interface.
*   **Adsgram Integration**: Monetize your bot by displaying advertisements to users.
*   **Self-Hosted Privacy**: You maintain full control over the data and history of your chatbot.
*   **Automation**: Use the bot to automate tasks like reminders, message scheduling, and data retrieval.

## 🧠 Managing Your Bot

The bot framework relies on a modular architecture. You can modify the behavior of the AI by updating the script files within the `/logic` directory. 

If you want to change how the bot replies to users, locate the `responses.py` file. This file contains the primary prompts that guide the AI. You can rewrite these lines in plain language. The bot adopts the personality or tone you define in these settings.

## 🛡️ Maintenance and Updates

Software updates occur periodically. Check the repository link occasionally to see if new versions exist. To update your local setup, download the latest files from the download link, extract them, and replace your existing folder. Ensure you copy your `config.json` file to the new folder to keep your keys and settings intact.

## 💡 Solving Common Problems

Most issues occur during the initial setup phase. Verify these points if the bot fails to start:

*   **Invalid Keys**: Double-check that your Telegram token and Google API key contain no extra spaces or hidden characters.
*   **Python Installation**: Ensure you have a current version of Python installed on your Windows machine. Visit the Python website to download the latest installer if necessary.
*   **Internet Access**: Firewalls sometimes block the connection between your computer and the Telegram servers. Ensure your security software allows the program to communicate over the network.
*   **Missing Libraries**: If you see an error about missing modules, type `pip install -r requirements.txt` into your command prompt window. This installs the necessary background tools.

## 🤝 Getting Help

The community surrounding this project contributes to its development. If you encounter errors, search the Issues section of the GitHub page. Many common setup questions have existing solutions provided by other users. 

You can also read the included documentation files located in the `docs` folder. These files contain technical details about the specific AI models used by the bot and advanced configuration options for experienced users. Keep your API keys private at all times. Do not share your configuration file with anyone.