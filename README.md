# Automatically upload screenshots from your computer into a discord channel

This program automatically uploads new screenshots that appear in a folder on your computer to Discord and posts them in a channel:

![Screenshot](http://i.imgur.com/QPS9V6f.jpg)

Point it at your Steam screenshot folder, or similar, and shortly after you hit your screenshot hotkey the screenshot will appear in your discord chat.

## What you'll need

* A folder where screenshots are stored
* A [discord webhook](https://support.discordapp.com/hc/en-us/articles/228383668-Intro-to-Webhooks)
* This program

## Getting started

### Binaries

TBD

#### From source

TBD

## Using it

`dau` is a command line driven program. When executed, it will continually scan a directory for new images, and each time it finds one it will upload it to discord, via the discord web hook.

`dau` will only upload "new" screenshots, where "new" means a file that appears in a directory that it is watching, if it appears *after* it has started executing.

Thus, you do not have to worry about pointing `dau` at a directory full of images, it will only upload new ones.

If `dau` is on your path, you can run it from your screenshot folder and there is then no need to specify the path to your images.

Note that currently `dau` does not look in subdirectories. Please submit an issue if this is a use case for you.

The only two mandatory command line parameters are the discord webhook URL:

`--webhook URL` - the webhook URL (see [here](https://support.discordapp.com/hc/en-us/articles/228383668-Intro-to-Webhooks) for details).

and the directory to watch:

`--directory /some/path/here` - the directory that screenshots will appear in.

You will have to quote the path on windows, or anywhere where the directory path contains spaces. Note that
subdirectories will also be scanned.

Other parameters are:

`--watch xx` - specify how many seconds to wait between scanning the directory. The default is 10 seconds.

`--username <username>` - an arbitrary string to show as the bot's username in the channel.

`--help` - show command line help.

`--version` - show the version.

## Limitations/bugs

* Only files ending jpg, gif or png are uploaded.
* If multiple screenshots occur quickly (<1 second apart) not all may be uploaded.

## TODO
This is just a quick hack. Open to suggestions on new features and improvements.

Open an [issue](https://github.com/tardisx/discord-auto-upload/issues/new) and let me know.
