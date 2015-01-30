# nodejs-logreplay #

## What?

__nodejs-logreplay__ is a (very) simple Node.js application which parses the standard Apache access log and replays the requests, in real time, and creates a logfile containing original requests (but with updated timestamps).  

## Why?

__nodejs-logreplay__ was developed to assist in load testing web server(s) by replicating the same request pattern that production systems experience.  This helps us determine how code modifications will perform in production before they are deployed. 

## How?

Easy:

1. Install Node.js and the reuqired packages via "npm install"

2. Clone this repository onto the server you wish to launch your load test requests from

3. Copy the provided configuration file `config/example.json.dist` to `config/<something>.json` and edit
 * `source`: Full path to the access log you want to replay
 * `output`: Full path to the output access log 
 * `speedupFactor`: Speed at which log is replayed (ie: 2 = twice normal speed) 


4. Run the profile you created (the `<something>` you chose in #3)

       ```node replay.js <something>```

## Who ??

This project is forked from https://github.com/adamlundrigan/nodejs-logreplay which replays request in realtime from a logfile against a target server (over http) - I've basically replaced the http related portions with a file output. This was because I wanted a tool to test logfile creation and piping into systems such as logstash, fluend and storm.


## Disclaimer

This code is provided AS-IS, with no warranty (explicit or implied) and has not been vetted or tested for deployment in a production environment. Use of this code at your own risk.

Released under Public Domain. Associated libraries carry their own individual licenses where applicable.


