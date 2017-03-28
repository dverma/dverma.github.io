---
layout: post
title:  "Juve Commentator"
date:   2017-03-28
excerpt: "Listen to the match highlights when they happen! "
tag:
- NodeJS
- Twitter
- API
- Say
- Football
- Text to Speech
image: 'https://cloud.githubusercontent.com/assets/1270335/24422920/d4bd8d50-13c0-11e7-9de6-20ee12635363.png'
feature: 'https://cloud.githubusercontent.com/assets/1270335/24422920/d4bd8d50-13c0-11e7-9de6-20ee12635363.png'
comments: true
---
# 🎤 Juve Commentator 

I built this app to silently run as a daemon on my raspberry pi and look for tweets from Juventus FC's twitter stream and on match days convert the tweets during the game into speech and announce it on the speaker.

## Motivation

The motivation behind this app was simple; being a huge juventus fan I wanted to stay updated with scores and important highlights as they happen (well, with the latency of someone watching and tweeting of course :stuck_out_tongue_closed_eyes: ).
Live Coverage of Serie-A in USA is very shoddy, most of the times the games aren't live on TV and sometimes there are delayed coverage.
Juventus' media team are exceptionally good in covering the matches with live tweets and that gave me the idea of building an app that could continuosly listen to the tweets and during the match convert selective tweets(filtered through some rules) related to the match  into speech and speak them out.

## Tech Stack

The app is built in NodeJS and uses the following modules:
* [Twitter](https://www.npmjs.com/package/twitter)
* [Say](https://www.npmjs.com/package/say)


## Minimum Requirements

You should have Node and npm installed. If you don't have them, install them from [here](https://nodejs.org/en/download/).
For the text-to-speech (tts)
* Mac OSX (comes with say)
* Linux with Festival installed
* Windows (comes with SAPI.SpVoice)

If you dont have Festival installed on your linux distro, try the following command to install Festival as well as a default voice:
```
sudo apt-get install festival festvox-kallpc16k
```

## Installation

```
git clone https://github.com/dverma/juve-commentator.git
cd juve-commentator
npm install
npm start
```
---

## Notes:

This app will also work for any team whose twitter live tweets the match news in a specific format.
```
A tweet that starts with a number followed by '(1', 29' representing the minute in game) or HALF-TIME or FULL-TIME
```
For ex: Real Madrid and AC Milan follow the same convention of live tweeting during a match. 

All you have to do to make this app work for your team is change the config.json to get the twitter id of the team's page from [here](http://gettwitterid.com/).
For ex. 452155423 for Real Madrid(realmadriden) or 186386857 for AC Milan(@acmilan) in api_params -> follow
To follow AC Milan replace api_params in config.json with :
```
  "api_params": {
      "stall_warnings": "true",
      "follow": "186386857",
      "track": ""
  }
```
