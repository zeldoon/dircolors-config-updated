# Modified config file for **dircolors** with correct installation steps
> Why post this? ***Everyone's instructions ARE FUCKING WRONG!*** They show a bunch of color/format codes but in the end, they just export the variables into BASH ENV


# Setup and Installation:
> ***NOTE: Without a path adjustment inside .bashrc you will need to place the config file directly into your home folder as a hidden file and use the default name.***
> ***So I will provide instructions using the default path set in .bashrc and assume you just want to copy/paste the text from the config file versus cloning over a repository***

+ Open your terminal to create an empty config file in the proper location:
> ```shell
> touch $HOME/.dircolors && nano $HOME/.dircolors 
> ```
+ Now copy/paste the contents of the config file into nano then save 
+ Open up your terminal to view the changes.
+ CONGRATS!

## More information on various installation options, modifications and what have you 
So I use pop! os and my go-to shell is tilix in quake mode, super useful having a shell that will drop down in whatever workspace I am in but there was one issue: the shell has the transparency set so I can read through it but when I'm on a page with a white background it's very difficult to read the shell's text.

This is where customizing the color values for everything came in handy. Instead of switching between two color profiles I decided to set the background on certain text


#Rant and Information why th


