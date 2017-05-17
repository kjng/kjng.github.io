---
published: true
---
## Setting up MongoDB in Windows

This is a quick guide to setup a MongoDB server on a Windows 10 computer using Chocolatey. It can be tough looking through many Stack Overflows and outdated online posts. This post has instructions that are up to date as of **5/17/2017**.

Most of this guide will be using administrator permissions when using Command Prompt or Powershell. If something doesn't work, try running as administrator!

### Chocolatey

First step, using Chocolatey, a Windows package manager, to install the MongoDB software. Head on over to [Chocolatey](https://chocolatey.org/install) and copying over the script to install it. Here is the **Command Prompt** script for reference:

> @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

### Adding MongoDB to PATH

MongoDB most likely won't be able to be ran using the `mongo` or `mongod` commands at this point. In order to register these aliases, press the start button on your keyboard and type `environment variables`. The result "Edit the system environment variables" is the one you want.

After the System Properties window opens, click on the "Environment Variables..." button. Next, highlight the Path variable and click the "Edit..." button under the "User variables for ...: table. If you don't currently have a Path variable, you'll need to press "New..." and make it.

In this Edit environment variable window, click "New" and add the filepath to your MongoDB installation. Usually, it's `C:\Program Files\MongoDB\Server\3.2\bin`.

Now you should be able to run MongoDB using the `mongod` command but we still have a few more steps.

### Creating data folders (\data\db)

MongoDB needs a place to store the databases and log files so we'll need to create that directory.

Within Powershell or Command Prompt, type `mkdir \data\db`. Make sure you're using backslashes or you'll get a syntax error. This will make the \data\db directories under your Local Disk directory for Mongo (C:\data\db).

### Setting up Windows service

Now, if you want MongoDB to run automatically without needing to open up a CMD-prompt and type mongod each time, let's register it as a Windows service to automatically run and shutdown on computer starts and shutdowns.

To do that, open up an administrator Command Prompt and run the following commands:

```
mongod --dbpath=C:\data\db --logpath=C:\data\db --install
net start MongoDB
```

The first command registers the service with Windows services as MongoDB specifying the location of the database (\data\db from earlier) as well as log file (same directory).

`net start MongoDB` then runs the service.

### Done!

Now you're all set to begin developing with a MongoDB server in a Windows 10 environment.
