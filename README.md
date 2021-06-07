# display_tweet_for_streaming
An animation and tool in HTML, CSS and JS to dispaly tweet in streaming tool that is supporting browser source

![Demo](https://raw.githubusercontent.com/tainalo2/display_tweet_for_streaming/main/tweet.gif)

# Summary
  - Prerequesites
  - Technical explanation
  - Installation
    - Nodered file host
    - Nodered import
    - Nodered configuration
  - Using
  - Credit


# Prerequesites
  - A nodered server (free low code GUI for NodeJS server) https://nodered.org/
  - Nodered libraries : node-red-dashboard; node-red-contrib-loop-processing

# Technical explanation
  We have two webpage, first to display a twitter feed with last tweet, you can click on it to send websocket message to display it on the second webpage.
  Second one waiting this message to run an animation and display the tweet.
  Nodered centralized the communication and is requesting the twitter API V2 to have tweets information.
  
# Installation
 - Nodered file host
   - create a directory called /home/user/node-red-static/
   - download and copy all your library files (xxx.js) content into that directory
   - you need library : anime.min.js (https://github.com/juliangarnier/anime/blob/master/lib/anime.min.js) and jquery.textfill.js (https://jquery-textfill.github.io/)
   - set httpStatic in your settings file to /home/user/node-red-static (line be like :  httpStatic: '/home/user/node-red-static/',)
   - restart Node-RED
   - check you can load http://YOUR_NODERED_IP:1880/xxx.js in your browser.
   - Credit for this chapter : Knolleary https://discourse.nodered.org/t/import-javascript-library-into-node-red/7665
 - Nodered import
   - Copy the content of the git file : "nodered_flow.json"
   - In nodered dashboard go to options and "Import"
   - Paste the file content and click "Import"
 - Nodered configuration
   - In node "iframe" replace "YOUR_NODERED_IP" by your nodered server IP
   - 
