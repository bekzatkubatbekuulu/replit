
import os
from background import keep_alive
import pip
pip.main(['install', 'pytelegrambotapi'])
import telebot
import time

bot = telebot.TeleBot('5701552410:AAGwuJT70YtoLTqL0A1BgKWUFd1IuD0q4pQ')

@bot.message_handler(content_types=['text'])
def get_text_message(message):
  bot.send_message(message.from_user.id,message.text)

keep_alive()
bot.polling(non_stop=True, interval=0)





from flask import Flask
from flask import request
from threading import Thread
import time
import requests


app = Flask('')

@app.route('/')
def home():
  return "I'm alive"

def run():
  app.run(host='0.0.0.0', port=80)

def keep_alive():
  t = Thread(target=run)
  t.start()





























