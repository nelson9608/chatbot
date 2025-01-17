# ChatBot

[![CI](https://github.com/deltachat-bot/chatbot/actions/workflows/python-ci.yml/badge.svg)](https://github.com/deltachat-bot/chatbot/actions/workflows/python-ci.yml)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

Conversational chat-bot for Delta Chat, using OpenAI API.

## Install

```sh
pip install git+https://github.com/deltachat-bot/chatbot.git
```

### Installing deltachat-rpc-server

This program depends on a standalone Delta Chat RPC server `deltachat-rpc-server` program that must be
available in your `PATH`. To install it check:
https://github.com/deltachat/deltachat-core-rust/tree/master/deltachat-rpc-server

## Usage

Configure the bot:

```sh
chatbot init bot@example.com PASSWORD
```

Create a configuration file named `config.json` in the program folder, for example:

```
{
  "api_key": "sk-...",
  "global_monthly_quota": 10000000,
  "user_hourly_tokens_quota": 4000,
  "user_hourly_queries_quota": 60,
  "openai": {
    "model": "gpt-3.5-turbo",
    "max_tokens": 500
  }
}
```

**Note:** On GNU/Linux the program folder is at `~/.config/chatbot/`, when configuring the bot it will
print the path to the accounts folder that is inside the configuration folder.

Start the bot:

```sh
chatbot serve
```

Run `chatbot --help` to see all available options.
