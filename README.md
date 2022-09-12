# How to Install and Configure Z Shell in Ubuntu

Z Shell (zsh) is a popular alternative to the default command line bash shell that offers several advanced features like recursive path expansion, automatic spelling correction for mistyped directory names, and plug-in and theme support. 

This guide will walk you through the process of installing and configuring zsh, including how to change themes as well as enable one of its most useful plug-ins, auto-complete suggestions. 

## Before You Begin

Prior to moving on, please complete the following steps:

### 1. Install [Git](https://git-scm.com/):

```
sudo apt install curl wget git
```

## Installation

### 1. Install [Zsh](https://zsh.sourceforge.io/):
```
sudo apt install zsh
```

### 2. Install [Oh My Zsh](https://ohmyz.sh/):
```
sh -c "$(curl -fsSL https://raw/github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

You should see the following prompt asking if you'd like to set your defaut shell to zsh. Press `y` to confirm. 

![Oh My Shell Configuration Prompt](oh-my-zsh-config-prompt.png)

{{< note >}}

If for any reason you need to switch back to the bash shell, use the following command and then log out and back into your session:
```
chsh -s $(which bash)
```
{{< /note >}}

## Change Zsh Theme
By default, the theme is set to `robbyrussell`, but there are over 100+ pre-bundled themes to choose from. 

For example, here are just of 3 of the several unique themes to choose from:

1. agnoster
![Agnoster Theme Preview](agnoster-theme-preview.png)

2. dispwoso
![Dispwoso Theme Preview](diswoso-theme-preview.png)

3. jonathan
![Jonathan Theme Preview](jonathan-theme-preview.png)

Here are the steps to change themes:

1. Open the zsh configuration file
```
vi ~/.zshrc
```
2. Press `i` to enter Insert Mode

![List of Bundled Zsh Theme Names](bundled-zsh-theme-names.png)

3. Change the ending of the line reading
```
ZSH_THEME="robbyrussell"
```
to
```
ZSH_THEME="desired-theme-name"
```

4. Press `:wq` to save and quit.

5. Reload the command line:
```
source ~/.zshrc
```

6. Check out your new themed command line and repeat steps 1-5 with a few more themes to find the best fit.

## Enable Auto-Complete Suggestions
The auto-complete suggestions plug-in is probably the single most useful tool in terms of saving time when having to type the same command over and over again. Instead of having to press `TAB` like normal auto-completion, the command line automatically suggests the rest of your command as you are typing

For example, rather than typing `git push origin main` every single time you wish to push a new commit, you can instead type `git push` and the command line will instantly show a shadow of the rest of the suggested command that matches your history.

![Auto-Complete Plug-in Preview](auto-complete-plug-in-preview.png)

Follow these steps to install and enable the plug-in:

1. Change directories to the oh-my-zsh plug-ins location 