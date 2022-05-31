# SketchCord
**Sketchcord** is used to send messages to **Discord** using Discord **Webhooks**. It is an unofficial API. Works great with **Sketchware**/Sketchware Pro/ Sketchware Revolution or Sketchware Gold.
## Hosting
To use it, you can use the default API, **https://sketchcord.heroku.app/api/send**. But If your app is too popular, you can host the API yourself. Just click the below button.
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/nicesapien-too/sketchcord/tree/main)
## Using
First, before we get started, Let me tell you the basic setup.
First you will need to add a `content-type` header with `application/json` value.
Then you will have to write json in Request body to specify your message.
Here are the available body params:

| Name        | Value       |
| ----------- | ----------- |
| content      | Main message       |
| username   | Username of  webhook      |
