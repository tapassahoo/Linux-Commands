# Welcome to the Linux-commands wiki!

- How do I jump to the location of my last edit? [see](https://vi.stackexchange.com/questions/2001/how-do-i-jump-to-the-location-of-my-last-edit)

-  Essential VIM commands [see](http://vim.wikia.com/wiki/Moving_around)

-  Essential VIM commands [see](https://www.catswhocode.com/blog/130-essential-vim-commands)

-  Copy and paste content from one file to another file in vi [see](https://stackoverflow.com/questions/4620672/copy-and-paste-content-from-one-file-to-another-file-in-vi)

- Linux diff command [see](https://www.computerhope.com/unix/udiff.htm)

- vi/vim delete commands and examples [see](https://alvinalexander.com/linux/vi-vim-delete-line-commands-to-end)

- vim cheat sheet [see](https://vim.rtorr.com)

- Setting Your PYTHONPATH environment variable (Linux/Unix/OsX) [see](https://scipher.wordpress.com/2010/05/10/setting-your-pythonpath-environment-variable-linuxunixosx/)

## Use of Rsync
- 6 rsync Examples to Exclude Multiple Files and Directories using exclude-from [see](https://www.thegeekstuff.com/2011/01/rsync-exclude-files-and-folders/?utm_source=feedburner)

- 3 Ways to Delete All Files in a Directory Except One or Few Files with Extensions [see](https://www.tecmint.com/delete-all-files-in-directory-except-one-few-file-extensions/)

- How to Use Rsync to Sync New or Changed/Modified Files in Linux [see](https://www.tecmint.com/sync-new-changed-modified-files-rsync-linux/)

- Rsync (Remote Sync): 10 Practical Examples of Rsync Command in Linux [see](https://www.tecmint.com/rsync-local-remote-file-synchronization-commands/)

- Way to exclude files from rsync while transferring those from remote to local machine

rsync -avze ssh graham:/home/tapas/ResultsOfPIGS/* /Users/tsahoo/ResultsOfPIGS/ --exclude 'PIGS-qTIP4P-RotDOFs-Rpt[01789].[02468]Angstrom*-beta0.2Kinv*System11-p-H2O*'

## Use of module

- User’s Tour of the Module Command [see](https://lmod.readthedocs.io/en/latest/010_user.html)

## How to execute a file in /usr/local/bin by using ./bash_profile

- How do I run a .sh or .command file in Terminal [see](https://apple.stackexchange.com/questions/235128/how-do-i-run-a-sh-or-command-file-in-terminal/235129)

- About bash_profile and bashrc on macOS [see](https://scriptingosx.com/2017/04/about-bash_profile-and-bashrc-on-macos/)

## Encrypt & Decrypt Files With Password Using OpenSSL
see [here](https://www.shellhacks.com/encrypt-decrypt-file-password-openssl/)
How to use OpenSSL to encrypt/decrypt files? see [here](https://stackoverflow.com/questions/16056135/how-to-use-openssl-to-encrypt-decrypt-files)

## ssh key generation on linux for Passwordless Login

- See [here](https://www.2daygeek.com/ssh-key-generation-on-linux-for-passwordless-login/)

## Schedule Tasks on Linux Using Crontab

- See [1](https://kvz.io/blog/2007/07/29/schedule-tasks-on-linux-using-crontab/), [2](https://www.tecmint.com/11-cron-scheduling-task-examples-in-linux/) and [3](https://www.cyberciti.biz/faq/how-do-i-add-jobs-to-cron-under-linux-or-unix-oses/)

## SSH Can Do That? Productivity Tips for Working with Remote Servers

- See [1](http://blogs.perl.org/users/smylers/2011/08/ssh-productivity-tips.html)

## FUSE and SSHFS on OS X

- See [1](https://stuff-things.net/2015/05/20/fuse-and-sshfs-on-os-x/), [2](https://blogs.harvard.edu/acts/2013/11/08/the-newbie-how-to-set-up-sshfs-on-mac-os-x/), [3](https://medium.com/@tzhenghao/writing-remote-code-on-a-mac-with-sshfs-c62d64bf9ef9), [4](https://blog.khairulazam.net/2013/06/05/write-failed-broken-pipe-issue-on-mac-os-x/)

## job handling by ~/.bashrc 
- To see a list of jobs which are pending 

```
alias pdlist=$'squeue -u tapas|awk \'$5==\"PD\"\''
```

- To see a list of jobs which are running
```
alias runlist=$'squeue -u tapas|awk \'$5==\"R\"\''
```

- list of jobid for pending jobs

```
alias killpd=$'squeue -u tapas|awk \'$5==\"PD\"\'|awk \'{print $1}\''
```

## gnuplot script

My gnuplot script (gnuplot-fitting) comprised the below line -

```
f(x) = a + b*x*x+c*x*x*x*x
a=-2500.
b=-10000000.0
c=-10000000000.0
#fit f(x) '< tail -8 ~/ResultsOfPIGS/PIGS-TransAndRotDOFs-Rpt10.0Angstrom-Energy-vs-tau-fixed-beta0.1Kinv-Blocks10000-Passes200-System2-p-H2O-preskip5000-postskip0.txt' using 2:6:10 yerrors via a, b, c
#plot '< tail -8 ~/ResultsOfPIGS/PIGS-TransAndRotDOFs-Rpt10.0Angstrom-Energy-vs-tau-fixed-beta0.1Kinv-Blocks10000-Passes200-System2-p-H2O-preskip5000-postskip0.txt' using 2:6 w lp, '' u 2:6:10 w yerr, f(x)
fit f(x) filename using 2:6:10 yerrors via a, b, c
plot filename using 2:6 w lp, '' u 2:6:10 w yerr, f(x)
pause -1 "Hit Enter to continue"
```

- To plot 'somefile', I run 
```
gnuplot -e "filename='< tail -8 ~/ResultsOfPIGS/PIGS-TransAndRotDOFs-Rpt10.0Angstrom-Energy-vs-tau-fixed-beta0.1Kinv-Blocks10000-Passes200-System2-p-H2O-preskip5000-postskip0.txt'" gnuplot_
```
