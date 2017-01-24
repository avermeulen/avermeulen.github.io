---
layout: post
title:  "Backup a remote mongodb database and restore it locally"
date:   2016-12-10
categories: mongodb databases ubuntu osx utilities
---

# Backup a remote MongoDB database and restore it locally

Recently I found myself using MongoDB alot and backing up remote databases and restoring it locally became part of my workflow.

I documented my workflow for future reference.

## On your Linux (I use Ubuntu) server:

Backup the database like this:

`mongodump --db your_db_name`

This will create a backup in `dump/your_db_name`

Zip all the files together in a tar file like this:

`tar -zcvf your_db_name.tar.gz dump/your_db_name`

After this you should have a `your_db_name.tar.gz` file in your current folder.

## On your PC

Use `scp` to copy the backup to your PC:

`scp <your server IP or domain name>:your_db_name.tar.gz ./`

Extract the backup files from the `tar` file like this:

`tar -zxvf your_db_name.tar.gz`

Then use `mongorestore` to restore a copy of the database locally. You can specify the target database using the `--db` option.

`mongorestore --db <target-db> dump/your_db_name`

Happy backing up and restoring MongoDB databases.
