# Python django with pm2
Python django app can run non stop on any server using pm2.


## Getting Started
### Steps

1. Install Node from given link
   https://nodejs.org/en/download/
2. Install npm using this command in command prompt / terminal
   npm install npm@latest -g
3. Run this command for execute django application non stop on server machine
   pm2 start echosystem.config.json

Description of echosystem.config.json

{
"apps": [{
"name": "djnago_with_pm2",
"script": "manage.py",
"args": ["runserver", "127.0.0.1:8000"],
"exec_mode": "fork",
"instances": "1",
"wait_ready": true,
"autorestart": false,
"max_restarts": 5,
"interpreter" : "python"
}]
}

If we have to change the port number of our django application,then we can the port no in args attribute of echosystem.config.json file.
After done the changes in echosystem.config.json file, stop the server using pm2 command like this:
 pm2 stop all // this command will stop all server.
 pm2 stop 0 // if you know the pm2 id then execute command like this.
 m2 start echosystem.config.json // again start the django application.
