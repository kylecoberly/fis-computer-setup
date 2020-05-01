## Watch a Video of These Instructions for MacOS:

[![Watch the video](https://img.youtube.com/vi/IgQbOZ1i6yM/maxresdefault.jpg)](https://youtu.be/IgQbOZ1i6yM)

Welcome student! Before we embark, let's turn your computer from a software _consumer_ computer to a software _developer_ computer. Follow each of these instructions _in order_. If something doesn't work, *stop* and try the step again. If it's still not working, ask an instructor for help before you move on!

Note: When you copy/paste a command from this page to your terminal, you *may need to hit enter after everything looks like its run!*. You might still have commands that need to run!

## Setup your terminal

Your terminal (which sometimes you'll hear referred to as a "shell" or "the command line" or a "CLI") will be your primary means of interacting with your computer in the program. This will take the place of navigating through file folders, downloading installers, and running programs by clicking on icons.

### MacOS

* Download and install [iTerm2](https://www.iterm2.com/)
* Open iTerm2
* Go to Profiles -> Open Profiles -> Edit Profiles -> General -> Command, and make sure "Login shell" is selected
* Close any open terminals with Command + Q, and reopen them

### Ubuntu

The default terminal for Ubuntu (GNOME Terminal) will work for this program. Make sure the following option is *checked*:

☰ -> Preferences -> Profiles -> Your Name -> Command -> Run command as a login shell

## Install Homebrew

For consumer software, you're probably used to going to a website, downloading a file, and running it on your computer to install it. For developer software, we use package managers to automate a lot of this.

### MacOS

Install [Homebrew](https://brew.sh/) by running this command on your terminal:

```bash
xcode-select --install ; /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

If you did this right, you should be able to run:

```bash
which brew
```

and something like `/usr/local/bin/brew` print out to your screen. If you didn't see anything print out to your screen, Brew didn't install correctly.

### Ubuntu

You already have a package manager installed called `apt`!

## Install some packages

Now, we'll use our package manager to download some helpful software we'll use in the program.

### MacOS

Run:

```bash
brew install git zsh gmp gnupg sqlite postgres
```

### Ubuntu

Run:

```bash
sudo apt update
sudo apt install git zsh gnupg sqlite postgresql postgresql-contrib
```
## Install `rvm` and Ruby

We'll use a tool called [`rvm`](https://rvm.io/) to have greater control over which version of ruby we're using.

### MacOs and Ubuntu

Run this command:

```bash
gpgconf --kill all
gpg2 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | bash -s stable --auto-dotfiles
export PATH="$PATH:$HOME/.rvm/bin"
[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
```

Remember to hit enter after everything is done!

Close out of all open terminal windows with Command + Q. Then, reopen iterm2.

If this worked correctly, running this in your console should print `rvm`:

```bash
command -v rvm
```

Then, run:

```bash
rvm install 2.6.1
rvm use 2.6.1 --default
```

Remember: Hit enter after you're done to be sure both commands ran!

If this worked correctly, running this command:

```bash
which ruby
```

should print something that looks like `/home/your-name/.rvm/rubies/ruby-2.6.1/bin/ruby` and *not* something like `/bin/ruby`.


## Install Ruby Gems

Gem is another package manager, like Homebrew. We'll use `brew` for installing software for our _computer_, and we'll use `gem` for installing software for our _projects_.

IMPORTANT NOTE: Never `sudo gem install` a gem. Gems can be published by well-intentioned developers, geniuses, students, and criminals. At any rate, you probably don't want to give them complete control over your computer.

### MacOS and Ubuntu

```bash
gem update --system
gem install rails learn-co bundler pg nokogiri pry
```

Hit enter when you're done!

If running:

```bash
which rails
```

prints something like `/home/your-name/.rvm/gems/ruby-2.6.1/bin/rails`, you're probably in good shape!

## Install `nvm` and Node

Just like rvm gives us more control over which version of Ruby is installed, [nvm](https://github.com/nvm-sh/nvm) does that for Node.

### MacOS and Ubuntu

Run the following command in your terminal:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

Hit enter when you're done!

If this worked, the following command should print `nvm`:

```bash
command -v nvm
```

If that worked, run the following command in your terminal:

```bash
nvm install node
nvm use node
nvm alias default node
```

Hit enter when you're done!

## Install Node Packages

Another package manager? Yep! Gem is for installing packages written in Ruby, and npm is is for installing packages written in JavaScript.

Run the following command in your terminal:

```bash
npm install -g yarn lite-server create-react-app
```

If running:

```bash
which lite-server
```

prints something to the screen, you're probably in good shape!

## Set up git

### MacOS and Ubuntu

Run these commands, swapping you `you@example.com` and `Your Name` for your actual email and name.

```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

Follow [these steps](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh) to connect your computer to Github

## Set up zsh

### MacOS and Ubuntu

Run:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

When it asks you if you want to switch your shell over to zsh, type "y" and hit enter.

The *close all open instances of your terminal*. When you reopen your terminal, your command prompt should have a colored `~` on it.

## Set up Learn

### MacOS and Ubuntu

Run:

```bash
learn whoami
```

And follow the instructions.

## Set up your text editor

You'll spend most of your time in the program in your text editor. If you already have a preference, keep using it! Switching text editors, even with the same file, is not a big deal. If you're looking for a suggestion, VS Code is a good place to start.

### MacOS

Download and install [VS Code](https://code.visualstudio.com/)

### Ubuntu

Run the following commands:

```bash
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
sudo apt update
sudo apt install code
```
