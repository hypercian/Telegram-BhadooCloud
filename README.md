# Bhadoo Cloud Testing

Original Docs by Creator at [creators-ReadMe.md](https://github.com/ParveenBhadooOfficial/Telegram-BhadooCloud/blob/master/creators-ReadMe.md)

## Watch Video
https://drive.google.com/file/d/1q5VVCCreOuXsujRzZkBAv12WJ1KZvQ0I/view

## Basic Documentation

* Fork this Repo
* Create a Telegram Bot
* Change Token in [Line 2](https://github.com/ParveenBhadooOfficial/Telegram-BhadooCloud/blob/master/src/.constants.js)
* Create a Folder inside you Google Drive, open it and Copy it's ID.
* For `https://drive.google.com/drive/folders/1p7pHhSh2yboWePmo53DnVr3xkAYiojP9` `1p7pHhSh2yboWePmo53DnVr3xkAYiojP9` is ID.
* client_secret.json already added. Don't change unless you know what you're doing.
* Start an EC2 AWS Virtual Machine or Your Own Linux Machine.
* `sudo apt update`
* `sudo apt upgrade`
* `sudo apt install aria2`
* `curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -`
* `sudo apt install nodejs`
* `sudo npm install -g typescript`
* `sudo git clone https://github.com/hypercian/Telegram-BhadooCloud`    Change this url to your fork url.
* `cd Telegram-BhadooCloud`
* `sudo npm install`
* `sudo tsc`
* `sudo bash ./aria.sh` It Should Print `Aria2c daemon started`
* `sudo npm start`
* `sudo reboot` is required
* `sudo bash ./aria.sh` It Should Print `Aria2c daemon started`
* `sudo npm start`
* Your Bot is Started. Send `/mirror https://github.com/hypercian/Telegram-BhadooCloud/blob/master/README.md` to your Telegram Bot.
* In Terminal Copy the accounts.google.com full url and paste in browser and authenticate your drive.
* Paste the Token you received in terminal.
* Download the credentials.json file from your Linux Server. (I use Termius to Transfer files, it's in root of Telegram-BhadooCloud directory)
* Your Bot is active and now we can deploy it on Heroku.
* But if you want to run it on EC2 instead of Heroku follow below.
* `sudo screen`
* This will run your bot in background even you close terminal. (otherwise Bot will go offline as soon as terminal session ends)

Note: You must change git url in [Docker File](https://github.com/ParveenBhadooOfficial/Telegram-BhadooCloud/blob/master/Dockerfile) on line 22.

## Deployment to Heroku

* Download and Install Heroku CLi and Bash.
* Create Account at Heroku and Create an App. (Note down Name you given it)
* Assuming Heroku App Name as xxxx
* Download your Repo after editing has been done of Token and Client ID and Secret.
* Extract it and Open bash by right clicking on that folder.
* Paste it in .constants.js file GDrive Directory Value.
* Download repo to your drive locally. (for windows right click in directory and open bash)
* Login to Heroku CLI
* `cd /d d:`    to change directory in windows here d: is D Directory changing from C.
* `heroku login`
* `git init`
* `heroku git:remote -a xxxx`
* `heroku stack:set container`
* `git add .`
* `git add -f credentials.json src/.constants.js aria.sh client_secret.json`
* `git commit -m 'try commit'`
* `git commit -am "make it better"`    commit any changes
* `git push heroku HEAD:master --force`
* `heroku ps:scale worker=0`
* `heroku ps:scale worker=1`
* Check your bot.
