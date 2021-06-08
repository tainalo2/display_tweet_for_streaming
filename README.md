# display_tweet_for_streaming
An animation and tool in HTML, CSS and JS to dispaly tweet in streaming tool that is supporting browser source

![Demo](https://raw.githubusercontent.com/tainalo2/display_tweet_for_streaming/main/tweet.gif)

# Summary
  - Prerequesites
  - Technical explanation
  - Installation
    - Twitter API registration
    - Nodered file host
    - Nodered import
    - Nodered configuration
    - Twitter API V2 research query, and the elevation to the trance meditation
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
 - Twitter API registration
   - You need to ask access to API dashboard as developper to twitter (use this link : https://developer.twitter.com/en/docs/twitter-api/getting-started/getting-access-to-the-twitter-api). It's a long process like French Bureaucracy. But after you will have all access needed instantly !
   - Once you have acces to dashboard : https://developer.twitter.com/en/portal/dashboard
   - Go to : https://developer.twitter.com/en/portal/apps/new and name your app and create it
   - Go to : https://developer.twitter.com/en/portal/projects-and-apps , find your application and click on the key icon
   - Front of "Bearer Token", click on "Regenerate", and  save your "Token" (NEVER SHARE IT !!!)
   - You are the best person in the world, be brave, never forget it, it's not a satanic incantation that will stop you !
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
   - In node "html tweet" replace "YOUR_NODERED_IP" by your nodered server IP, on line 42
   - In node "html tweet_display" replace "YOUR_NODERED_IP" by your nodered server IP, on line 53, 54 and 58
   - In node "http request", in "token" parameter pull your twitter bearer token
 - Twitter API V2 research query, and the elevation to the trance meditation
   - You have the token, the key of the power, but now you have to master the weapon !
   - The most important is here : method to research what you want from twitter. All is in the URL !
   - First, you have to understand the difference between "URL language" and "Full string parameter"
   - URL language is what web server will treat as functionality
   - Full string parameter is what web server don't treat and have to eliminate special "URL language" character to not be interpreted
   - In example "?query=" is treat as "URL language" because "?" aand "=" can be intrpreted, but in "?query=%23DLNS%20-is%3Aretweet" : "%23DLNS%20-is%3Aretweet" are "Full string parameter" waited by twitter service but where URL special character has been replace by URL string format to not be interpreted. So %23 will be understand as the string "#", %20 is a common space " ", and %3 replace ":".
   - To traduce full string to URL encoding go here : https://www.w3schools.com/tags/ref_urlencode.ASP
   - To simply find recent tweets about a hashtag, in node "http request" > URL > replace "DLNS" by your hashtag
   - To create your own request go to those documentations : 
   - Search/recent API V2 : https://developer.twitter.com/en/docs/twitter-api/tweets/search/api-reference/get-tweets-search-recent
   - How to build queries : https://developer.twitter.com/en/docs/twitter-api/tweets/search/integrate/build-a-query
   - Index of all API V2 requests : https://developer.twitter.com/en/docs/api-reference-index

# Using
- Go to http://YOUR_NODERED_IP:1880/ui and find your twitter feed OR integrate it has a docker directly in OBS with http://YOUR_NODERED_IP:1880/tweet
- In your broadcast software create a browser source with URL : http://YOUR_NODERED_IP:1880/tweet_display ; width : 600; height : 400
- When you click on a tweet it will display it, click button "End Animation" to hide it
- Enjoy, i'm already hype to see your show !

# Credit
Create by tainalo2 : french streamer on twitch every week day from 07H to 09H (Paris hours)
All my links here : https://linktr.ee/tainalo2
