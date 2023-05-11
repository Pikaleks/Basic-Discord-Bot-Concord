
# Workshop Discord bot in C - Beginner

This Workshop is an introduction of Concord - C Discord API library


## Install Concord

Clone Concord repo

```bash
    git clone https://github.com/cogmasters/concord.git && cd concord
```
```bash
    sudo make install
```

## Init bot

Go to your Discord app and activate the developer mode

Dev portal:

Go to the discord dev portal : https://discord.com/developers/applications

Click on **New Application** and give it a name

Click on **Bot** and click on **Reset Token** then **Yes, do it!**

Copy the token somewhere

Allow all Gateway Intents below

Go to **OAuth2** then **URL Generator** and select **bot** and **Administrator**

Then copy the link and paste it in your browser

Create a server or use an existing one and add the bot

## Files

For the file structure you can use the same as your C project

* src folder

* include folder

* Makefile
    * you can use the same makefile you use for your C project
    * and make sure to add thos flags :
    * **-pthread -ldiscord -lcurl**

* config.json
    * you can use this copy paste it in your config.json
    ```json
    {
        "logging": {
            "level": "trace",
            "filename": "bot.log",
            "quiet": false,
            "overwrite": true,
            "use_color": true
        },
        "discord": {
            "token": "PUT YOUR TOKEN HERE",
            "default_prefix": {
                "enable": false,
                "prefix": "YOUR PREFIX HERE"
            }
        }
    }
    ```
    * just replace **PUT YOUR TOKEN HERE** by your token
    * and **YOUR PREFIX HERE** by your prefix

## Exercice 1 - Launch the bot

Make the main function that launch the bot and free it when the bot is stopped

## Exercice 2 - Ready event

Make the ready function that print **Bot is ready** in the console when the bot is ready

Find a way to change :
    * the bot status (online, idle, dnd, invisible)
    * the bot activity type (playing, streaming, listening, watching)
    * the bot activity text
