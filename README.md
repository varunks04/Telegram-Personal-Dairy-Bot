# Daily Reflection Bot

A Telegram bot that helps users track daily activities and provides AI-powered reflection and analysis.

## Features

- **Daily Diary Entries**: Record your thoughts, activities, and experiences
- **AI Analysis**: Get insightful analysis of your day with specific sections:
  - Gratitude points
  - Time management analysis
  - Memorable moments
  - Habit pattern analysis
  - Day summary
  - Suggestions for improvement
  - Overall day rating
- **Audio Summaries**: Receive audio versions of your diary analysis
- **Personal Bio**: Customize your experience with personal information for more tailored analysis
- **Diary Archive**: Access and review past entries

## Setup Instructions

### Prerequisites

- Python 3.8+ installed
- Telegram Bot Token (from [@BotFather](https://t.me/BotFather))
- OpenRouter API Key for AI analysis

### Installation

1. Clone the repository or download the source code

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Create an `.env` file in the project root directory with the following variables:
```
BOT_TOKEN=your_telegram_bot_token_here
OPEN_API_KEY=your_openrouter_api_key_here
AI_MODEL=openai/gpt-3.5-turbo
ALLOWED_USER_IDS=123456789,987654321
```

4. Run the bot:
```bash
python bot.py
```

### Environment Variables

- `BOT_TOKEN`: Your Telegram bot token obtained from BotFather
- `OPEN_API_KEY`: Your OpenRouter API key for AI analysis
- `AI_MODEL`: The AI model to use (default: "openai/gpt-3.5-turbo")
- `ALLOWED_USER_IDS`: Comma-separated list of Telegram user IDs that are allowed to use the bot

## Directory Structure

The bot automatically creates the following directory structure:

```
DATA/
├── Audio/              # Temporary storage for audio files
├── Diary/              # Raw diary entries organized by month
├── DiaryEntries/       # Processed diary entries with analysis
└── Users/              # User-specific bio information
```

## Usage

### Commands

- `/start` - Initialize the bot
- `/help` - Display help information
- `/diary` - Begin a new diary entry
- `/setbio` - Set your personal information for better analysis
- `/mydiary` - List your recent diary entries
- `/read_YYYYMMDD` - Read a specific diary entry

### Workflow

1. Start a diary entry with `/diary` or by saying "hi"
2. Write about your day
3. The bot will analyze your entry and ask if you want audio
4. Receive your analysis in text (and optionally audio) format
5. Access past entries with `/mydiary` and `/read_YYYYMMDD`

## Security Features

- User authentication via whitelisted Telegram IDs
- Input sanitization for all user inputs
- Path traversal protection
- Error handling and logging

## Privacy Considerations

- All data is stored locally on the server running the bot
- Personal information is only used to enhance the analysis
- No data is shared with third parties except for the diary text sent to OpenRouter for analysis

## Dependencies

See `requirements.txt` for a complete list of dependencies.

## License

[MIT License](LICENSE)

## Troubleshooting

If you encounter any issues:

1. Check that all environment variables are correctly set
2. Ensure the bot has write permissions to create directories
3. Verify your OpenRouter API key is valid
4. Check the logs for detailed error messages

For additional help, please open an issue on the project repository.
