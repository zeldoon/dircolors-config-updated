# Modified config file for **dircolors** with correct installation steps
Why post this? ***Everyone's instructions didn't work for me!*** 
They show a bunch of color/format codes but in the end, they just export the variables into BASH ENV
I have put all the standard color codes in the config file for you and added a bunch of extensions grouped into categories in case you tend to look for certain files. One neat option I like is setting orphan links to have flashing red text with a black background

# Setup and Installation:
> ***NOTE: Without a path adjustment inside .bashrc you will need to place the config file directly into your home folder as a hidden file and use the default name.***
> ***So I will provide instructions using the default path set in .bashrc and assume you just want to copy/paste the text from the config file versus cloning over a repository***

+ Open your terminal to create an empty config file in the proper location:
 ```shell
 touch $HOME/.dircolors && nano $HOME/.dircolors 
 ```
+ Now copy/paste the contents of the config file into nano then save 
+ Open up your terminal to view the changes.
+ CONGRATS!

### Easy method with curl
+ Open your terminal and use the following command to download the file to the correct location and name
 ```shell
 curl https://github.com/zeldoon/dircolors-config-updated/blob/d2e95ca75caf17318e13a81167e9c0cd0ff4e37c/.dircolors -o $HOME/.dircolors
 ```

## More information on various installation options, modifications and what have you 
So I use pop! os and my go-to shell is tilix in quake mode, super useful having a shell that will drop down in whatever workspace I am in but there was one issue: the shell has the transparency set so I can read through it but when I'm on a page with a white background it's very difficult to read the shell's text as I have everything set up for dark mode.
> I mean just look at this lovely readable text on a bright white page
> ![ls-a output](https://github.com/zeldoon/dircolors-config-updated/assets/20314483/93a7a324-c5ab-441e-b059-5eb26ee16d7e)


This is where customizing the color values for everything came in handy. Instead of switching between two color profiles, I decided to set the background on certain text to black so I could always read it but holy fuck was there a bunch of nonsense information out there regarding customizing dircolors or LS_COLORS. 

**some examples:**
 
[man page for dircolors on man7](https://man7.org/linux/man-pages/man1/dircolors.1.html) 

![dircolors-manpage-ex1](https://github.com/zeldoon/dircolors-config-updated/assets/20314483/31710e99-b7cb-483d-8c91-f51ff8bcdeaf)

cool... now most sites tell you to slap in dircolors -b which then spits out this:
LS_COLORS='rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:'; export LS_COLORS

So now you are thinking... well I'll just add this to my .bashrc, edit what I want, save and $ source .bashrc, and then I will have my custom setup.
One of my favorite people to read tips from: [ itsfoss article on ls_colors ](https://itsfoss.com/ls-color-output/)

Hrmm worked for a bit but now it's messed up. Now why is this?

![dircolors script in bashrc](https://github.com/zeldoon/dircolors-config-updated/assets/20314483/c0d4e20d-0691-4033-b87c-a2295fa69f91)

so in .bashrc you have a line you probably never put much thought into but if you notice it throws the -b flag for bash format but it sets the default location to look for your custom config file to .dircolors ...
***So if you want a better location for this file you will need to edit this line to point to your preferred location***

