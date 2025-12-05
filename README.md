from flask import Flask, jsonify
import random

app = Flask(__name__)

jokes = [
    "چرا کامپیوترها انقدر باهوش هستند؟ چون به اینترنت وصل هستند!",
    "تفاوت بین یک برنامه‌نویس و یک شعبده‌باز چیه؟ شعبده‌بازها خرگوش از کلاه درمیارن، برنامه‌نویس‌ها باگ!",
    "چرا برنامه‌نویس‌ها طبیعت رو دوست ندارن؟ چون توش دیباگ کردن خیلی سخته!",
    "وقتی یک برنامه‌نویس مریض میشه چی میگه؟ میگه: int main()",
    "چرا گربه ها برنامه نویس خوبی نیستن؟ چون در دیباگ کردن تنبل اند"
]

channel_link = "https://t.me/your_channel_username"  # لینک کانال تلگرام خود را اینجا قرار دهید

@app.route('/joke')
def get_joke():
    joke = random.choice(jokes)
    response = {
        'joke': joke,
        'channel_link': channel_link
    }
    return jsonify(response)

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=5000)
