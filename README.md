# AI_Agent
AI Agent for Cryptocurrency Price Fetching and Language Translation
This repository contains the implementation of a simple AI agent that can fetch cryptocurrency prices (specifically Bitcoin) and handle basic language translation requests. The agent uses the LLaMA 3.1 8B model from Together AI for handling user interactions and performing language translation tasks. It also integrates with an external public API to fetch cryptocurrency prices.

Table of Contents
1. Overview
2. Installation
3. Usage
4. Features
5. Example Conversations
6. Assumptions and Limitations
7. Error Handling
8. License
9. Overview
The AI agent:

Uses the Together AI API to integrate with the LLaMA 3.1 8B model for understanding user queries and performing actions.
Fetches real-time cryptocurrency prices for Bitcoin (BTC) and Ethereum (ETH) via a public API.
Handles language translation requests and maintains English as the primary communication language for the system's responses.
Allows for conversation flow, where context is maintained across multiple messages.
Implements error handling for API calls to ensure smooth interaction.
Installation
Prerequisites:
Python 3.7+ (recommended)
openai and requests libraries
A valid Together AI API key for accessing the LLaMA model
A valid CoinMarketCap API key (for fetching cryptocurrency prices)
Steps to Set Up:
Clone this repository:

bash
Copy
Edit
git clone https://github.com/yourusername/crypto-lang-ai-agent.git
cd crypto-lang-ai-agent
Create a Python virtual environment (optional but recommended):

bash
Copy
Edit
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
Install required dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Set up your environment variables for API keys:

Create a .env file in the root directory of the project and add the following:
plaintext
Copy
Edit
TOGETHER_API_KEY=your_together_api_key
CMC_API_KEY=your_coinmarketcap_api_key
Load the environment variables in the code (using python-dotenv).

Run the agent:

bash
Copy
Edit
python agent.py
Usage
Once the agent is set up and running, you can interact with it via the command line. The agent listens for user queries and can respond to requests like:

"What is the price of Bitcoin?"
"Translate 'How are you?' to Spanish."
"What is the price of Ethereum?"
The agent will maintain context across multiple messages, making it capable of understanding follow-up questions and performing tasks accordingly.

Example Workflow:
You can ask:

"What is the price of Bitcoin?"
The system will fetch the Bitcoin price and return it to you.
You can ask a translation query:

"Translate 'Hello, how are you?' into Tamil."
The system will respond with the translated text in Tamil.
The agent will continue the conversation, remembering the previous interactions.

Features
Core Features:
Cryptocurrency Price Fetching: The agent fetches live Bitcoin and Ethereum prices from CoinMarketCap using their public API.
Language Translation: The agent can handle basic translation requests and ensures all system responses are in English.
Conversation Flow: The system maintains context across multiple queries to ensure a smooth and consistent conversation.
Bonus Features:
Rate Limiting: Rate limiting is implemented to prevent overloading the CoinMarketCap API with too many requests.
Caching: API results are cached to reduce unnecessary calls and improve performance.
Example Conversations
Conversation 1:

pgsql
Copy
Edit
User: What is the price of Bitcoin?
Assistant: The current price of Bitcoin (BTC) is $45,000 USD.

User: What about Ethereum?
Assistant: The current price of Ethereum (ETH) is $3,500 USD.
Conversation 2:

sql
Copy
Edit
User: Translate 'Hello, how are you?' into Spanish.
Assistant: The translation of 'Hello, how are you?' in Spanish is: "Hola, ¿cómo estás?"

User: Now translate 'How are you?' into French.
Assistant: The translation of 'How are you?' in French is: "Comment ça va ?"
Assumptions and Limitations
Assumptions:

The cryptocurrency symbols are mapped correctly (e.g., "Bitcoin" is converted to "BTC" and "Ethereum" to "ETH").
The translation system only supports text-to-text translation without advanced linguistic capabilities.
Limitations:

The system is limited to fetching only Bitcoin (BTC) and Ethereum (ETH) prices.
The translation feature currently supports basic translations and may not handle complex phrases or idioms perfectly.
The system may encounter rate limiting when too many requests are made in a short period (due to CoinMarketCap’s API restrictions).
Error Handling
The agent implements error handling for:

API request failures (e.g., CoinMarketCap API errors)
Network errors
Incorrect user input or unrecognized queries
In case of errors, the assistant will print the message:

arduino
Copy
Edit
"Sorry, something went wrong. Please try again."
This ensures that the agent doesn’t crash unexpectedly and provides a smooth user experience.

License
This project is licensed under the MIT License - see the LICENSE file for details.
