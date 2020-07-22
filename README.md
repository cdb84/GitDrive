# GitDrive
A collection of scripts to turn git-scm into a viable cloud storage provider

## What it is

GitDrive is a collection of scripts that synconize files between a remote git server and your local machine. Using them, you can create a self-hosted cloud storage platform that operates in a similar way to OneDrive. You can use this, for example, to sync home folders between machines. 

## How it works

The user's home directory is cloned as a git repo from a remote server. Then, the iwatch script is started. The iwatch script will watch for updates to the filesystem under the user's home directory. If there is an update, then another script will add the file to the git repo and commit it with an automated yet easily traceable commit message. Then, a cron job pushes the repo every 2 minutes, and pulls it every 3. Following this paradigm, a user's home directory can be syncronized between machines in a similar way to how OneDrive allows Windows users to syncronize Desktop, Documents and other user files between Windows machines.

## Dependencies

iwatch, git

## Infrastructure

A remote machine running as a git-scm server is preffered, as GitHub has a maximum upload size of 100mb (and it would also be rude to store your entire home directory on github.)
