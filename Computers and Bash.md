---
up:
  - "[[500 Alexandria]]"
stardate: Oct 14th 2023
update: Oct 14th 2023
---
## CPU and GPU

My GPU is Intel with 16GB. CUDA is a tool to speed up Deep Learning, and runs on Nvidia GPUs (which is what Hossein has).

We have 8 cores - Janus has 64

- Double format is the same as a 64-bit float.
- 16-bit floats can handle 3 decimal places, and 32-bit floats can handle 6 decimal places

```bash
# To run scripts remotely on Janus without getting locked out:
nohup Rscript script.r &
# To get progress, 
tail -f nohup.out
# To kill a running job,
# Get PID with
ps aux | grep script.r
# And terminate it with
kill PID
```

## Bash basics
[Intro to Shell](https://hbctraining.github.io/Intro-to-shell-flipped/schedule/links-to-lessons.html)
```bash
# create a txt file
cat > file.txt
touch file.txt
# list files in a text file
ls *.md > markdownfiles.txt
# append list of files to new text file
ls *.md >> markdownfiles.txt

# show path to file
which file
type -p file

# assign file to variable
n < markdownfiles.md

#changes all the instances of the word `markdown` to `software` in the first 5 `*.md` files in your current directory
ls *.md | head | sed -i `s/markdown/software/g`

# create a python script
touch script.py

# manual page for a command
man cmd

# edit the file (or create if it doesn't exist)
nano file.txt
# ctrl X will ask to save the file before exiting

# move file to current directory
mv tmp/filename .
#copy file to current directory
cp tmp/filename .

# to show exactly one character
?

# see file
less file.txt
cat file.txt

# or if it's long
more file.txt
# to leave window use q

# install multiple packages at once
pip install -r file.txt
# with the packages listed in file.txt

# get the packages installed in the correct format for a txt file to be installed in a different directory
pip freeze > packages.txt

#set aliases
alias python='/usr/bin/python3'

# changing ownership and rights
sudo -i #login as root user
# give everyone permission to alter a file
sudo chmod a+rwx /usr/lib
# remove a directory recursively
rm -rf directory/

# make a directory
mkdir my_project

```


![[Computers and Bash-1.png]]
### Manage files

```bash
###### grep looks for strings in files ######
# search for a string within a file
grep "string" file.txt
# search for a string that is COMPLETE within a file ("strings" will not be returned, only string)
grep -w "string" file.txt
# include lower and upper case
grep -wi "string" file.txt
# include line number of occurrence
grep -win "string" file.txt
# search recursively within the directory
grep -winr "string" .
# show only the names of files that have this string
grep -wirl "string" .

# sync files across different directories
rsync Original/* Backup/

###### find looks for files in directories ######
# find all directories
find . -type d
# find all files
find . -type f
# given subdirectories, how far do you want to go?
-mindepth n
-maxdepth n
```

### Loops
```bash

for varname in list
do
    command1 $varname
    command2 $varname
done


COUNTER=0
while [ ${COUNTER} -lt 10 ]; do
    command 1
    command 2
    COUNTER=`expr ${COUNTER} + 1` 
done


```

### Shell scripts

The `echo` command is used to display a line of text that is passed in as an argument. This is a bash command that is mostly used in shell scripts to *output status to the screen or to a file.*
``` bash
echo "Your current working directory is:"
pwd

echo "These are the contents of this directory:"
ls -l

#### what to add to a shell script to run experiments
#!/bin/bash
source /home/aavila/forest_regrowth/venv/bin/activate
script=./file.py
python3 $script

```

echo can also show the contents of a variable:
```bash
echo $num
# remember $ indicates variables
```

### Fedora initial setups

```bash
# Making tab autocomplete case-insensitive
echo 'set completion-ignore-case on' | sudo tee -a /etc/inputrc

# Removing brackets from paste
echo 'set enable-bracketed-paste off' | sudo tee -a /etc/inputrc

# install dconf-editor and disable audible-bell
sudo dnf install dconf-editor
gsettings set org.gnome.desktop.sound event-sounds false

# install github CLI for https authentication
sudo dnf install gh

# for tidyverse and other R packages
sudo dnf install libcurl-devel openssl-devel proj-devel geos-devel sqlite-devel udunits2-devel

# upgrade all packages and their dependencies
sudo apt-get dist-upgrade

# curl and httr packages may need to be installed for other packages to run
R -q -e "install.packages(c("curl", "httr", "openssl", "tidyverse", # required for tidyverse in Fedora
                   "terra", "rstan", "cmdstanr", "ggplot2",
                   "remotes", "Rcpp", "sf", "terra" # required for terra
                   ))"
```

### Add Python to ipykernel for jupyterlab
/home/anazonia/Documents/forest_regrowth/forest_env/bin/python -m ipykernel install --user --name 'forest_env'