//ADD THIS IN THE MAIN FILE , IN THE TOP AS SHOW IN THE VIDEO
 
from webserver import keep_alive   
import os
 
 
 
 
 
//REMOVE THE client.run("Token") Line And Add This
 
 
 
 
 
 
keep_alive()
 
TOKEN = os.environ.get("DISCORD_BOT_SECRET")
 
client.run(TOKEN)
 
 
 
 
//NOW MAKE A NEW FILE NAME webserver.py AND ADD THIS CODE INSIDE IT.
 
 
from flask import Flask
 
from threading import Thread
 
 
 
app = Flask('')
 
 
 
@app.route('/')
 
def home():
 
    return "I'm alive"
 
 
 
def run():
 
  app.run(host='0.0.0.0',port=8080)
 
 
 
def keep_alive():  
 
    t = Thread(target=run)
 
    t.start()
