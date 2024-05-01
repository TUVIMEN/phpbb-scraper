# phpbb-scraper

A bash script for scraping phpbb forums in json.

## Requirements

 - [reliq](https://github.com/TUVIMEN/reliq)
 - [jq](https://github.com/stedolan/jq)

## Installation
    
    install -m 755 phpbb-scraper /usr/bin

## Supported links formats

    http(s)?://forum.com/(.*/)?viewtopic.php.*[\&\?]t=[[:digit:]]+.*
    http(s)?://forum.com/(.*/)?viewforum.php.*
    http(s)?://forum.com/(.*/)?index.php.*
    http(s)?://forum.com/.*

## Json format

Here's example of [topic](topic-example.json).

## phpbb 1.x support

As of now 1.x versions are not supported, mainly because of how lax their implementation is.

## Supported phpbb 2.x examples

    http://forum.moyeamedia.com/index.php
    http://forum.anime-ultime.net/phpBB3/index.php
    http://missosology.info/forum/index.php
    https://garaz.autorevue.cz/index.php
    https://forum.mobilmania.zive.cz/index.php
    https://forum.avmania.zive.cz/index.php
    https://www.eurobabeforum.com/index.php
    https://www.eldemore.com/index.php
    http://askcodeman.com/index.php
    http://forum.mthbuilt.com/index.php
    http://forum.akusherstvo.ru/index.php
    https://forum.motec.com.au/index.php
    https://forum.ecc.kz/index.php

## Supported phpbb 3.x examples

    http://www.phpbb.pl/index.php
    https://fungi.pl/forum/index.php
    https://forum.asustor.com/index.php
    https://stilldcf.com/forums/index.php
    https://www.ao-universe.com/forum/index.php
    https://forum.aegean.gr/index.php

## Usage

    phpbb-scraper [URL]...

Script downloads topic to files named by their id's.

Download forum into current directory using 4 processes

    phpbb-scraper -p 4 'https://stilldcf.com/forums/viewforum.php?f=3'

Download topic by irregular topic url into DIR 

    phpbb-scraper -d DIR -t 'https://forum.com/abcdef/loop/'

Download whole forum

    phpbb-scraper 'http://missosology.info/forum/index.php'

Get some help

    phpbb-scraper -h
