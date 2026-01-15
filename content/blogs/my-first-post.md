---
title: "Welcome to my Blog"
date: 2026-01-14
description: "This is my very first post on my new portfolio site."
image: ""
author: "Lalita Segal"
tags: ["General"] # <--- Add this line exactly like this!
---

### Setting up a GitHub Repository!

Today I'm going to show you how to set up a repository on GitHub and get it moved and working into VSCode using the Terminal.

You'll be able to create your website by writing code in the Terminal window via VSCode. I did this for my website because I wanted to do it on a budget (free) and this is a good way to do it while learning Terminal.

First thing is to create a [GitHub]() account if you haven't already. It is free to setup and use. According to Wiki:
![GitHub Wiki Screenshot](/images/githubwiki.jpg)

You can also host your projects there on a website, like mine!

Once you create a GitHub account you'll be in your dashboard and you press the green "New" button.
![GitHub NewButton](/images/githubnewbutton.jpg)

This will allow you to create your repository which is where your code will be for your project.
Next download [VSCode for Mac]() if you haven't already.

Once you have VSCode you'll want to open it up and then open a new Terminal window using the + or the shortcut Ctrl + ~ or you can go to the top menu: Terminal > New Terminal.

Next you'll want to make sure it opens as zsh (Z Shell).

**Zsh is the environment in your Terminal that interprets the commands you type.**

Your VSCode could be setup a little different than mine so the Terminal might be on the side or bottom. As you can see it has zsh.
![Zsh](/images/zsh.jpg)

**Also a side note, ensure your Mac is updated to the most recent OS. As you read this I am on Sequoia 15.7.3 (soon to upgrade to Tahoe).**

Next use the shortcut: _CMD + Shift + P_ and type in "shell command" then select **Shell Command: Install 'code' command in PATH.**

This will allow you to type _code_ in any Terminal to open that folder in VSCode.

Common ways to use this command:

- _code_ : Typing this inside any folder in your terminal will instantly open that entire folder in VS Code.
- _code filename.txt_ : This opens a specific file directly in VS Code from the terminal.
- _code -n :_ This opens a brand new, empty VS Code window.
- _code -d file1.js file2.js_ : This opens the two files side-by-side in "diff" mode so you can see the differences between them.

**Now for the fun part.** You get to put in some command lines in Terminal so you can configure your GitHub. You need to tell GitHub who you are first. So using the Terminal you opened we need to check if GitHub is installed already (most likely not if this is the first time using any of these).

**Type this in Terminal:**
_git --version_
If it returns a version number then great! It's already installed, but if it's asking you to install "command line developer tools" then click **install**.

**Now you need to set your identity:** run these two commands, replace the placeholders with your information.

- _git config --global user .name "Your Name"_
- _git config --global user .email "your-email@example.com"_

A side note. I recommend typing out all this code by hand even if it feels a bit sloggy. That way you will learn more rather than just copy/pasting it in Terminal. Don't forget all the spaces and dashes and periods. All of it needs to be typed out exactly as it shows otherwise it won't work.

**Its time to connect a project to GitHub**
We are going to link a folder on your Mac to that new GitHub repository you setup.

1st. **Initialize:** In VSCode Terminal type _git init_
2nd. **Add files**:** type: \*git add
3rd. **Create commit:** _git commit -m "First commit"_
4th. **Copy URL\*\* Copy the URL of your repository.

If you've never used or are relatively new to GitHub it can be confusing where to find it. But it's easy! In the repository you created you'll see a green <> Code button. Click on that and it shows your URL. Click the two little squares to copy it!
![Copy Code from Git](/images/copycode.jpg)

5th. **Connect to GitHub**: In your VSCode Terminal type: _git remote add origin Paste_Your_URL_Here_ and hit enter
6th. **Push your code:** Type in _git push -u origin main_

Since we are setting up your GitHub project in VSCode it is unlikely you've done this before and therefore will be asked to sign in. However it's a little tricky as you can't use the password you created when you setup your GitHub, you will need to generate a **Personal Access Token (PAT)** instead.

In GitHub click on your profile picture on the top right of the page and go to **Settings**. Then on the left sidebar scroll to the bottom and click on **<> Developer Settings**

![GitHub Settings](/images/gitsettings.jpg)
![GitHub Dev Settings](/images/gitdevsettings.jpg)

Select: **Personal access tokens** > **Tokens (classic)**

Click: **Generate new token** > **Generate new token (classic)**

![GitHub Token](/images/newtoken.jpg)

Configure your token:

- \**Give it a name under *Note\*,
- \*\*Set the expiration date, or no expiration (use at your own risk)
- **Select scopes:** Check just the _repo_ box for now
- \*\*Scroll to the bottom to generate token

_[WARNING] You need to copy this token immediately before clicking out of the page and save it somewhere safe, like a notes document. GitHub will never show it to you again and if you lose it you will have to generate a new one._

Now that you have your token generated (and saved) go back to VSCode. Remember we were going to put in your GitHub username and password? Hopefully it is still up otherwise you will have to follow the steps above again.

Type in Terminal your GitHub username, hit enter and then the GitHub token you generated. I recommend just copy/pasting it this time as you will not see it show up on Terminal. This is a safety feature.

Once you pasted the token into Terminal hit enter.

**_Once again remember to save your token somewhere safe!_**

And now for one more command. To prevent your Mac from asking for the token every single time, you can tell Git to use the macOS keychain:

In your VSCode Terminal, run this:
First type in _Bash_ and hit enter.

_Side Note_: What is Bash? <---eventually add a link for a longer explanation. (Bash stands for **Bourne Again SHell** and just like **Zsh** it's a shell or the engine that lives inside your Terminal and processes code you type. If you think of your computer as a car, the Terminal is the dashboard and the shell is the engine under the hood)

Then type in this code _git config --global credential.helper osxkeychain_

And there you have it! You should have successfully setup your GitHub repository in VSCode and now you can start coding things!
