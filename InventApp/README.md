# InventApp - Smart Inventory Management Bot

## Overview
InventApp is an intelligent inventory management system that uses Telegram as its interface. This repository contains a simplified version of the original InventApp, focusing on core functionalities while maintaining the AI-powered features. The original version includes additional capabilities such as advanced reporting, multi-user support, and custom analytics.

## Version Information
### Simplified Version (This Repository)
- Basic product management (add, view)
- Voice command support
- Daily expiration notifications
- AI-powered command processing
- Single-user focused

### Original Version (Full Features)
- Advanced product management (add, remove, modify, view)
- Multi-user support with role-based access
- Custom reporting and analytics
- Advanced notification system
- Product categorization
- Batch operations
- Historical tracking
- Custom export options
- Advanced AI processing for complex queries

## Key Features
- **Telegram Integration**: Add products through Telegram messages
- **Voice Commands**: Support for voice-to-text commands
- **AI-Powered Processing**: Intelligent parsing of user commands
- **Daily Notifications**: Automated alerts for products nearing expiration
- **Database Storage**: Products stored in Supabase
- **Multi-language Support**: Built-in support for English and Spanish

## Technical Stack
- **n8n**: Workflow automation platform
- **Supabase**: Database storage
- **Telegram Bot API**: User interface
- **OpenAI**: Voice-to-text and command processing
- **AI Models**: For natural language understanding

## Project Structure
```
InventApp/
├── workflows/           # n8n workflow files
├── docs/               # Documentation
├── README.md          # This file
└── LICENSE.md         # MIT License
```

## Getting Started

### Prerequisites
- n8n instance (self-hosted or cloud)
- Telegram Bot Token
- Supabase account
- OpenAI API key

### Setup Instructions

1. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/InventApp.git
   cd InventApp
   ```

2. **Configure n8n**
   - Install n8n if you haven't already
   - Start your n8n instance

3. **Set up Credentials in n8n**
   
   a. **Telegram Bot**
   - Create a new bot using @BotFather on Telegram
   - Get your bot token (API key)
   - In n8n, create a new Telegram credential with your bot token
   - After saving, n8n will give you a credential ID
   - Replace `YOUR_TELEGRAM_CREDENTIAL_ID` in the workflow with the ID n8n provided
   - Replace `YOUR_TELEGRAM_CREDENTIAL_NAME` with a descriptive name for your credential

   b. **Supabase**
   - Create a new project in Supabase
   - Get your project URL and API key
   - Create a new Supabase credential in n8n with your API key
   - After saving, n8n will give you a credential ID
   - Replace `YOUR_SUPABASE_CREDENTIAL_ID` in the workflow with the ID n8n provided
   - Replace `YOUR_SUPABASE_CREDENTIAL_NAME` with a descriptive name for your credential

   c. **OpenAI**
   - Get your OpenAI API key
   - Create a new OpenAI credential in n8n with your API key
   - After saving, n8n will give you a credential ID
   - Replace `YOUR_OPENAI_CREDENTIAL_ID` in the workflow with the ID n8n provided
   - Replace `YOUR_OPENAI_CREDENTIAL_NAME` with a descriptive name for your credential

4. **Import the Workflow**
   - Go to your n8n instance
   - Import the workflow from `workflows/inventapp_simplified.json`
   - Activate the workflow

5. **Set up Supabase Database**
   - Create a new table called `products` with the following columns:
     - `id` (uuid, primary key)
     - `name` (text)
     - `quantity` (numeric)
     - `unit` (text)
     - `expiration_date` (date)

## Usage
1. Start a chat with your Telegram bot
2. You can add products in two ways:
   
   a. **Text Message**
   ```
   add 5 kg rice expiring on 2024-12-31
   ```
   
   b. **Voice Message**
   - Send a voice message saying something like:
   "Add 5 kilograms of rice expiring on December 31st, 2024"

3. **Daily Notifications**
   - The bot will automatically check for products nearing expiration
   - You'll receive a notification at 10 AM every day
   - Products with 5 or fewer days until expiration will be listed

## Language Support
The system supports both English and Spanish. To switch languages:

1. **English Version**
   - Default language
   - Commands in English
   - Notifications in English

2. **Spanish Version**
   - Commands in Spanish
   - Notifications in Spanish
   - Voice recognition optimized for Spanish

To implement a different language version:
1. Clone the base workflow
2. Update the prompts and messages in the AI nodes
3. Modify the notification templates
4. Update the command recognition patterns

## Security Note
This is a demonstration version of the project. Make sure to:
- Keep your API keys secure
- Use environment variables for sensitive data
- Regularly update your dependencies

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Author
Santiago Iino Cotado - 

## Acknowledgments
- n8n team for the amazing workflow automation platform
- Supabase for the backend services
- OpenAI for AI capabilities
