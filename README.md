# Solarized Everything

Resources and dotfiles to ensure, that most, if not all of your system is in

✨ SOLARIZED DARK ✨  

Instructions are based on Manjaro i3, including installation, but I'll drop
some links to the repositories.
I'm obviously skipping the ones, where it's easy to find in the settings. 
(IntelliJ etc.)

This repo is mirrored on [GitHub](https://github.com/alindl/solarized-everything) and [GitLab](https://gitlab.com/alindl/solarized-everything).  

// TODO check `~/.Xresources` colors  
// TODO use `~/.Xresources` colors

## Table of Contents
=================

   * [Solarized Everything](#solarized-everything)
      * [Table of Contents](#table-of-contents)
      * [Ranger](#ranger)
      * [(DOOM) Emacs](#doom-emacs)
      * [i3(-gaps)](#i3-gaps)
      * [~/.Xresources](#xresources)
      * [dunst](#dunst)
      * [Spotify (using spicetify-cli)](#spotify-using-spicetify-cli)
      * [GtK](#gtk)
      * [Firefox](#firefox)
         * [Theme](#theme)
         * [Dark Reader (aka. what if the whole Internet was solarized dark?)](#dark-reader-aka-what-if-the-whole-internet-was-solarized-dark)
         * [DuckDuckGo](#duckduckgo)
      * [Slack](#slack)

## Ranger

Find your `rc.conf` file. It's probably in `~/.config/ranger/rc.conf`.  
Look for this line(around line number 100): `set colorscheme default`  
or whatever theme is chosen instead of `default` and change it to   
`set colorscheme solarized`  
If it is not there, just add this line.  

## (DOOM) Emacs

Locate your `config.el`. (`~/.doom.d/config.el`)  
Find the part where you `(setq doom-theme 'doom-one)` and change it to  
`(setq doom-theme 'doom-solarized-dark)`  
Of course, if you can't find the line, just add it.  

## i3(-gaps)

You could probably do that through `.Xresources`, but I figured that out  
afterwards. I'm aware that there is a comment above this segment explaining   
just that in the i3 file.  

Speaking of which, find the i3 config file,  
which is located here: `~/.i3/config`.  
Close to the end of the file, you should find something that looks like  
the following lines, but with differend hex values or even stuff like `color0` or `background`  
Obviously, change it to those values:  

```
    colors {

     separator  #93a1a1
	   background #002b36
	   statusline #eee8d5

#                              border  backgr. text
            focused_workspace  #2aa198 #2aa198 #073642
            active_workspace   #657b83 #333333 #073642
            inactive_workspace #073642 #073642 #2aa198
            urgent_workspace   #cb4b16 #cb4b16 #073642
    }
}


# Theme colors
# class                   border  backgr. text    indic.  child_border
  client.focused          #2aa198 #2aa198 #073642 #FDF6E3 #2aa198
  client.focused_inactive #073642 #073642 #2aa198 #454948 #073642
  client.unfocused        #073642 #073642 #1ABC9C #454948 #073642
  client.urgent           #CB4B16 #FDF6E3 #1ABC9C #268BD2
  client.placeholder      #000000 #0c0c0c #ffffff #000000

  client.background       #2B2C2B
```


## ~/.Xresources

The title says it all, you need to change your file,  
so these values should look like this:  
(This is not the whole file, just the lines that should be changed.  
I'm not even sure if this is needed or correct,  
it's just what my file looks like)  


```
! special
*.foreground:   #93a1a1
*.background:   #002b36
*.cursorColor:  #93a1a1

! black
*.color0:       #002b36
*.color8:       #657b83

! red
*.color1:       #dc322f
*.color9:       #dc322f

! green
*.color2:       #859900
*.color10:      #859900

! yellow
*.color3:       #b58900
*.color11:      #b58900

! blue
*.color4:       #268bd2
*.color12:      #268bd2

! magenta
*.color5:       #6c71c4
*.color13:      #6c71c4

! cyan
*.color6:       #2aa198
*.color14:      #2aa198

! white
*.color7:       #93a1a1
*.color15:      #fdf6e3


XTerm*background: #2b2b2b
XTerm*foreground: #e7e7e7
XTerm*pointerColor: #16A085

*fadeColor:                       black
*pointerColorBackground:          #2B2C2B
*pointerColorForeground:          #16A085
```

## dunst

See `dunstrc` file in this repository.  
I put in the whole file, you can obviously delete the ones you don't see fit.  
  
On your system, you can find this file in `~/.config/dunstrc`  

## Spotify (using spicetify-cli)

Install `spicetify-cli` and `spicetify-themes-git`  
`yay -S spicetify-cli spicetify-themes-git` for Arch-based distros using `yay`  

Repositories:
[spicetify-cli](https://github.com/khanhas/spicetify-cli)
[spicetify-themes](https://github.com/morpheusthewhite/spicetify-themes)

(If you have any issues installing, read   
https://github.com/khanhas/spicetify-cli/wiki/Installation#linux-and-macos   
and other parts of their wiki.  
The following is the usual case that they suggest, I copied it from there.)  
  
Run this command to generate the config file:  
`spicetify`  
  
Make sure config file is created successfully and there is no error, then run:  
`spicetify backup apply enable-devtool`  
  
Throw in this one for good measure, shouldn't really do anything:  
`spicetify update`  
  
Go into this repository and copy the `SolarizedDark` folder that's in   
`spicetify` and put it in your own `~/.config/spicetify/Themes/` folder.  
(There is probably already one in there with the same name, I made some  
improvements though)  
  
Select the theme we just copied in:  
`spicetify config current_theme SolarizedDark`  
  
Apply the settings:  
`spicetify apply`  

## GtK

The way I install this could be Manjaro i3 specific, I'm not sure if `bmenu`  
comes preinstalled with arch.  
Nevertheless, if you have pure Arch, you will figure it out.  
  
Install `gtk-theme-numix-solarized`  
`yay -S gtk-theme-numix-solarized` for Arch-based distros using `yay`  

Repository:
[numix-solarized-gtk-theme](https://github.com/Ferdi265/numix-solarized-gtk-theme)
  
Open your `bmenu` (Mod+Ctrl+b is preconfigured for that on Manjaro-i3)  
-> System & Settings (7)  
-> Appearance (1)  
-> Set GTK2 Theme (1)  
Find `NumixSolarizedDarkCyan` in this list, put in the corresponding number,  
push the enter key.  
  
-> Set GTK3 Theme (2)  
Find `NumixSolarizedDarkCyan` in this list, put in the corresponding number,  
push the enter key.  
  
That's it, all saved. You maybe have to close and open any GtK apps   
for these changes to take hold.  

## Firefox

### Theme
There are solarized dark themes, but I don't like the color mapping of  
the ones I tested. I use the add-on [Zen Fox](https://addons.mozilla.org/firefox/addon/zen-fox/) instead  
Install that and of course, switch from light to dark.  

### Dark Reader (aka. what if the whole Internet was solarized dark?)
You may already know [Dark Reader](https://addons.mozilla.org/firefox/addon/darkreader), with which you can change the  
Internet to be in dark mode. But did you know,   
that you can change the color scheme?  
  
Click on the little icon in your Navbar  
-> go to `Dev Tools` (it's at the bottom right)  
-> click `Preview new design`.  
  
Now your menu should look a bit different.  
  
Click the icon again.  
-> Go to `See all options`, `colors`.  
-> Change `Background` to #002b36 (Don't forget to hit the enter key)  
-> Change `Text` to #93a1a1 (Enter key)  
  
That's it!  

### DuckDuckGo

Go to the [DuckDuckGo front page](https://duckduckgo.com/)  
-> Click the burger menu (top right)  
-> Themes  
-> Appearance  
  
Change all these fields:  

```
Background Color:                                     #002b36
Header Color:                                         #073642 
Result Title Color:                                   #fdf6e3
Result Visited Title Color:                           #93a1a1
Result Description Color:                             #839496
Result URL Color:                                     #2aa198
Result Hover, Module, and Dropdown Background Color:  #073642
```
_Save and Exit_ at the bottom and you are done.  


## Slack

Preferences (clicking your profile pic or on the workspace)  
-> Themes  
Obviously choose Dark  
Additionally, under `Colors` there's this field, with the description:  
_Copy and paste these values to share your custom theme with others_  
where you just paste in this:  
`#073642,#002B36,#B58900,#FDF6E3,#CB4B16,#FDF6E3,#2AA198,#DC322F,#002B36,#FDF6E3`  
