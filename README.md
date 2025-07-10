# Notis

Notis is an app on the FLECS-Marketplace for sending notifications.

## Usage

### User

As a user you just have to install notis via the FLECS-Marketplace and configure how notifications should be sent.
The app is not intended to be used directly by a user, instead your other apps can send notifications via notis.

You can configure notis by editing the config file `config.json` inside the `notis-config` volume of the installed app.
Look [here](https://github.com/FLECS-Technologies/notification-service) for the possible configurations.

### App developer

Your app can send notifications via notis by using the http REST API. If notis is installed it is reachable via the
hostname `flecs-notis`. If you just want to send a notification via the default service you can do so by posting a
`title` with an optional `content` to `/notifications`. Example using curl:
```curl -X POST flecs-notis/notifications --header "Content-Type: application/json" --data '{"title": "Hello", "content": "Hello from myApp" }'```

For more advanced use cases like configuring different services or even implementing your own notification type look
at the underlying open source
project [notification-service](https://github.com/FLECS-Technologies/notification-service#configuration).