# ISTS20-Botnet
Botnet server and bot code for ISTS 20

# Concept
Each team is given the ip of a C2. They will be given a binary for a bot which they must start and distribute to other boxes throughout the competition. The goal is to have a bot on as many boxes as possible. Teams are scored on what percentage of the network they have bots on every half hour. 

# Implementation Specs
+ Python Flask Server
+ SQLite Database Scoring 
+ Docker/Docker Compose
+ C/C++ Bots

# Web App End-Points
+ Linux - `/<team>/<ip>/linux`
+ Windows - `/<team>/<ip>/windows`
+ Main Page 
  + Score of each team at all times
  + No log in required 
 
# Admin End-points 
> Admin End-points requires admin token 
+ Admin end-point for getting a tally of each team's score - `/admin/score`
+ Ends the round, resets the scores, and returns the most recent scores - `/admin/reset`
+ Add and remove points - `/admin/edit`
+ Set IPs - `/admin/sethosts`
+ Get IPs - `/admin/gethosts`
+ Optional: List which teams have which boxes - `/admin/getCallbacks`

# Bot Features
+ Gather IP of the box it is put onto 
+ Send IP and team number to C2
+ Recieve unique command each time from the C2
+ Run command
+ Give output to C2
+ If any failure occurs, print "cannot connect" 
+ Runs with HTTPS so teams do not sniff in network scans  



# TODO
- Admin allowed to run custom commands
