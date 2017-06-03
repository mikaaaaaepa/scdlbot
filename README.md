# [Music Downloader Telegram Bot](https://t.me/scdlbot)

### Environment variables
#### Required
- `SC_AUTH_TOKEN` - Obtained from https://flyingrub.github.io/scdl/
- `TG_BOT_TOKEN` - Obtained from https://t.me/BotFather
- `STORE_CHAT_ID` - Chat ID for storing audios for inline mode

#### Optional
- `DL_DIR` - downloads dir (rewritten on every request!), default: `$HOME/dl_dir`
- `BIN_PATH` - custom directory where `scdl` and `bandcamp-dl` are available

### Used sites and libraries
- [Telegram Bot API](https://core.telegram.org/bots/api): [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot)
- [SoundCloud](https://soundcloud.com): [scdl](https://github.com/flyingrub/scdl)
- [Bandcamp](https://bandcamp.com): [bandcamp-dl](https://github.com/iheanyi/bandcamp-dl)
- [YouTube](https://www.youtube.com/): [youtube-dl](https://rg3.github.io/youtube-dl)
- Maybe would use [SoundScrape](https://github.com/Miserlou/SoundScrape) in the future


### Deploying to [Heroku](https://heroku.com/)

Install [Heroku Toolbelt](https://toolbelt.heroku.com/), then:

```
cd scdlbot
# Login to Heroku
heroku login
# Create app with python buildpack
heroku create --buildpack heroku/python
# Set python buildpack for upcoming builds
heroku buildpacks:set heroku/python
# Deploy your app to heroku
git push heroku master
# Set config vars
heroku config:set SC_AUTH_TOKEN='<SC_AUTH_TOKEN>' TG_BOT_TOKEN='<TG_BOT_TOKEN>' STORE_CHAT_ID='<STORE_CHAT_ID>'
# Start 1 worker dyno
heroku ps:scale worker=1
# Or stop worker dyno
heroku ps:stop worker
```

- https://devcenter.heroku.com/articles/dynos
- https://devcenter.heroku.com/articles/config-vars

https://soundcloud.com/n3rdynastya/hazyxn3rdy
https://soundcloud.com/b2band/moj-rock-n-roll
https://shitmat.bandcamp.com/album/killababylonkutz-2