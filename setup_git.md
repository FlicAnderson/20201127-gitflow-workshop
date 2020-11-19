# Setup Information for Lab Git Workshop

Author: Flic Anderson

Date: 19 Nov 2020


## Installing git

[Here's](https://git-scm.com/downloads) a great resource for how to download and install `git` on your machine!

It has options for different operating systems: 
 - [Windows](https://git-scm.com/download/win)
 - [Mac](https://git-scm.com/download/mac)
 - [Linux](https://git-scm.com/download/linux)

Once you've downloaded and run the installer file or run the command, you should be good to go!

Git often installs a commandline and GUI (Graphical User Interface) version on Windows. 

You can use either commandline or a GUI to interact with `git`, but I prefer the commandline, because I don't have to learn anything 'extra' to use it on computer clusters or storage systems etc.


## Configuring git repos

Git might ask you to configure a few things, and usually always asks you about your username and email.

These are the username and email which you'd use for any kind of service you use to remotely store, back up & manage your repositories.

Examples of these services are: 
- [GitHub](https://github.com/)
- [GitLab](https://about.gitlab.com/)

To add those details, `git` will often prompt you to add them via commands like this: 
```
$ git config --global user.name "Flic Anderson"
$ git config --global user.email "Flic@whatever.ema.il"
```

But you also need to think about the fact that your email and name might be visible in the details of any public repositories you might have there, so you can also keep your email address private if you use `GitHub` service for example, by using this format: `username@users.noreply.github.com` where you pop your username in, instead of `username`. You put this into the `git config --global` line as if it was your normal email address. 

The `--global` part of those commands just shows `git` that you want these details to be used for every project. 
