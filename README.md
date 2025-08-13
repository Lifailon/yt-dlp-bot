# YT-DLP Telegram Bot

Telegram bot that allows you to download videos from YouTube, Twitter, Reddit and many other socials using [yt-dlp](https://github.com/yt-dlp/yt-dlp) 

[Use the Bot](https://t.me/SatoruBot)

> [!IMPORTANT]  
> The Telegram [API limits](https://core.telegram.org/bots/features#local-bot-api) files sent by bots to 50 MB.

## Usage

In the bot private chat just send the video url, otherwise use `/download <url>`

## Self hosting

> [!NOTE]
> Before launching, you need to create your Telegram bot using [@BotFather](https://telegram.me/BotFather) and get its `API Token`.

- Clone the repository and install dependencies:

```bash
git clone https://github.com/ssebastianoo/yt-dlp-telegram
cd yt-dlp-telegram
pip install -r requirements.txt
cp example.config.py config.py
```

- Set your bot's `token` variable in the `config.py` file.

- Launch the bot:

```bash
python3 main.py
```

## Docker

Create a working directory, download the [docker-compose](./docker-compose.yml) file, set the bot token and run the container using the image from Docker Hub:

```bash
mkdir yt-dlp-bot
cd yt-dlp-bot

curl -sSL https://raw.githubusercontent.com/Lifailon/yt-dlp-bot/refs/heads/master/docker-compose.yml -o docker-compose.yml

echo '
token = "TELEGRAM_APU_KEY_YOUR_BOT"
logs = 2390049
max_filesize = 50000000
' > config.py

docker-compose up -d || docker compose up -d
```