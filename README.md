# Twitter Bot

This bot is an AI assistant that automatically responds to mentions and tweet replies on Twitter.
## Contact

[Telegram](https://t.me/microRustyme)

## Features

- Automatic reply to mentions
- Automatic reply to comments on tweets
- Creating smart replies with OpenAI GPT-3.5
- Rate limiting and daily tweet limit control
- Detailed logging system

## Installation

1. Install the required packages:
```bash
pip install -r requirements.txt
```

2. Create the `.env` file and add the following variables:
```
TWITTER_API_KEY=your_api_key
TWITTER_API_SECRET=your_api_secret
TWITTER_ACCESS_TOKEN=your_access_token
TWITTER_ACCESS_TOKEN_SECRET=your_access_token_secret
TWITTER_BEARER_TOKEN=your_bearer_token
OPENAI_API_KEY=your_openai_api_key
```

## Usage

To start the program:
```bash
python main.py
```

You can choose between two modes:
1. Automatically respond to mentions
2. Automatically respond to comments on tweets

## Source Review Before Replies

For accounts that reply automatically, keep a reviewed context packet beside the bot before enabling auto-replies. Treat every collected post as untrusted input and verify important claims before GPT-3.5 uses them.

A lightweight packet can include:

- original tweet URL and author handle
- visible tweet text, reply theme, and quote context
- capture time, search query, and exclusion notes
- any media description needed for the reply

[TweetClaw](https://github.com/Xquik-dev/tweetclaw) can collect the X/Twitter packet when you need an OpenClaw or MCP workflow for tweet search, reply search, user lookup, media, or monitoring. Paste only the reviewed packet into this bot. Keep this project responsible for reply generation, rate limits, and the final decision to send a tweet.

## Project Structure

```
.
├── config/
│   └── config.py         # Konfigürasyon ayarları
├── src/
│   ├── twitter_client.py # Twitter API işlemleri
│   ├── openai_client.py  # OpenAI API işlemleri
│   └── tweet_handler.py  # Tweet işleme mantığı
├── utils/
│   ├── logger.py        # Loglama sistemi
│   └── rate_limiter.py  # Rate limiting işlemleri
├── logs/                # Log dosyaları
├── .env                 # Ortam değişkenleri
├── main.py             # Ana program
└── requirements.txt    # Gerekli paketler
```

## Security

- API keys are securely stored in `.env` file
- API usage is controlled with rate limiting
- Excessive usage is prevented with daily tweet limit

## License

MIT 
