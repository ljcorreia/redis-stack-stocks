# Introduction

This project demonstrates how you can use the multi-model capabilities of Redis to create a real-time stock watchlist application. It uses several different features of Redis:

- Sets
- Pub/Sub
- Hashes
- RedisTimeSeries
- RedisBloom
- RedisJSON
- RediSearch

# Requirements

1. Install Docker

Set the following environment variables:

1. `APCA_API_KEY_ID`: Your Alpaca API Key found on the Alpaca dashboard
1. `APCA_API_SECRET_KEY`: Your Alpaca API Secret found on the Alpaca dashboard

# Installation

```
$ docker-compose up -d
```

After the containers are up and running, go into the `data` directory and run:

```
$ pip install -r requirements.txt
$ python main.py
```

# Known Issues

1. There is a known issue with the Alpaca websocket API thread safety. Right now if you watch/unwatch a stock you will need to restart the stream container, as it will silently halt when you try to dynamically update websocket subscriptions.
