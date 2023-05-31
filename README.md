
# Workshop Discord bot in C - Beginner

This Workshop is an introduction of Concord - C Discord API library


## Install Concord

Clone Concord repo

```bash
    git clone https://github.com/cogmasters/concord.git && cd concord
```

Compile Concord

```bash
    sudo make
```

If a curl error appear, install curl and compile again

```bash
    sudo dnf install libcurl-devel
```

Then install Concord

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
                "enable": false
            }
        }
    }
    ```
    * just replace **PUT YOUR TOKEN HERE** by your token

## Warning

You can find everything you need in the documentation
Even the solution of the exercices
But try to do it by yourself first, you can also ask us for help
Have fun :D

## Library

https://cogmasters.github.io/concord/

## Exercice 1 - Launch the bot

Make the main function that launch the bot and free it when the bot is stopped

## Exercice 2 - Ready event

Make the ready function that print **Bot is ready** in the console when the bot is ready

Find a way to change :
    * the bot status (online, idle, dnd, invisible)
    * the bot activity type (playing, streaming, listening, watching)
    * the bot activity text

## Exercice 3 - Ping Pong

Make a fonction that reply **Pong!** when the bot receive **ping** in a message

*Bonus* : add the latency of the bot in the reply

## Exercice 4 - Roles selection

Make a function that send a button with multiple roles

When a user click on a role the bot give him the role

## Exercice 5 - 8ball

Make a function that reply a random answer when the bot receive a message starting with **<prefix>8ball**

You are free to use the answers you want to display but here is a list of answers you can use :
    
```c
char *phrases[] = {
    "It is certain.",
    "It is decidedly so.",
    "Without a doubt.",
    "Yes definitely.",
    "You may rely on it.",
    "As I see it, yes.",
    "Most likely.",
    "Outlook good.",
    "Yes.",
    "Signs Point to Yes.",
    "Reply hazy, try again.",
    "Ask again later.",
    "Better not tell you now.",
    "Cannot predict now.",
    "Concentrate and ask again.",
    "Don't count on it.",
    "My reply is no.",
    "My sources say no.",
    "Outlook not so good.",
    "Very doubtful.",
};
```

## Exercice 6 - Help command

Make a function that send a message with all the commands of the bot and their description using embeds

## Exercice 7 - Shell

Make a function that simulate a shell in Discord

It work like your minishell but in Discord :D

## Bonus

* Do every command in slash commands
* Any other feature you want to add
