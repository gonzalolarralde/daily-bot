# daily-bot

# Set up
1. `cp config.yml.example config.yml`
1. Edit `config.yml` ([see "Config File"](#config-file))
1. `bundle install`

## Config File
Check an [example file here](config.yml.example).

### Mandatory tokens (Telegram)
```
telegram:
  token: telegram_token
  chat_id: chat_id
```

⚠️ __This key / values are mandatory.__
- `token` is the token you get when you setup a new bot. See: ["Bots: An introduction for developers"](https://core.telegram.org/bots#6-botfather).
- `chat_id` whom is the bot going to message. See: ["How to get a group chat id?"](https://stackoverflow.com/a/32572159)

### Script
#### covid
```
- type: covid
  country: argentina
```
`covid` shows a summary with daily increments about COVID-19 cases. 

:warning: __You have to specify the country.__

#### dollar
```
- type: dollar
```
`dollar` shows the dollar (blue and oficial) exchange rate in Argentina 💸

#### random_message
```
- type: random_message
  messages:
    - random message 1
    - random message 2
    - random message 3
```
`random_message` posts one random message 

#### random_gif
`random_gif` will post a gif that contains one tag from the ones you specify.

```
script:
  - type: random_gif
    tags:
      - firs tag
      - second tag
      - third tag

giphy:
  token: giphy_token
```

[Get an API Token](https://developers.giphy.com).

#### vaccines
```
- type: vaccines
```
`vaccines` posts a COVID-19 vaccine daily stats from Argentina.

#### weather
```
script:
- type: weather
  city: Buenos Aires
  
openweather:
  token: openweather_token
```
`weather` will post some current weather information (`weather_forecast` is cooler). 

[Get an API Token](https://openweathermap.org/api)

#### weather_forecast
```
script:
- type: weather_forecast
  lat: -34.586217
  lon: -58.477769
  
openweather:
  token: openweather_token
```
`weather_forecast` will show a daily forecast given an specific location. 

[Get an API Token](https://openweathermap.org/api)

## Run the app

1. Make sure you have added your bot into the channel (or group) you want.
1. `ruby app.rb`


## Run this daily
I used [cron jobs](https://en.wikipedia.org/wiki/Cron)

## Tests
```
make test
```
