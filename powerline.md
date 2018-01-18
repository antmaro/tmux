# Powerline in RHEL7 for Bash and Tmux

## To install powerline for tmux in RHEL 7

* Install the needed packages:

`$ sudo yum install -y tmux python-pip git`

* Install powerline from pip

`$ pip install --user git+git://github.com/Lokaltog/powerline`

* Installing Powerline fonts in Linux

`wget https://github.com/powerline/powerline/raw/develop/font/PowerlineSymbols.otf`

`wget https://github.com/powerline/powerline/raw/develop/font/10-powerline-symbols.conf`

* Move the fonts downloaded to your fonts directory and update your system's font cache:

`# mv PowerlineSymbols.otf /usr/share/fonts/`

`fc-cache -vf /usr/share/fonts/`

* Now install the fontconfig file:

`# mv 10-powerline-symbols.conf /etc/fonts/conf.d/`

## Enable Powerline on Bash Shell
Get the location of installed powerline via pip

``` bash
$ pip show powerline-status
Name: powerline-status
Version: 2.6.dev9999-git.a4a1c8353924959188d62c9edcf977cce3aa231f
Summary: The ultimate statusline/prompt utility.
Home-page: https://github.com/powerline/powerline
Author: Kim Silkebaekken
Author-email: kim.silkebaekken+vim@gmail.com
License: MIT
Location: /home/amarirom/.local/lib/python2.7/site-package
`

Once you know the location of powerline you have to add the following lines in your .bashrc:

``` bash
POWERLINE_BASH_CONTINUATION=1
POWERLINE_BASH_SELECT=1
. /home/amarirom/.local/lib/python2.7/site-packages/powerline/bindings/bash/powerline.sh
```

## Enable Powerline in TMUX
In the ~/.tmux.conf (or .tmux) file config you should add:

``` bash
source ~/.local/lib/python2.7/site-packages/powerline/bindings/tmux/powerline.conf
set-option -g default-terminal "screen-256color"
```


