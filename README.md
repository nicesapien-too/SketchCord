# SketchCord
**Sketchcord** is used to send messages to **Discord** using Discord **Webhooks** by sending **http requests**. It is an unofficial (REST)API. Works great with **Sketchware**/Sketchware Pro/ Sketchware Revolution or Sketchware Gold.
## Hosting
To use it, you can use the default API, **https://sketchcord.vercel.app/api/send** or **https://sketchcord-production.up.railway.app/api/send**. But If your app is too popular, you can deploy the API yourself. Just click the below button to deploy on Heroku.


[![Deploy on Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/nicesapien-too/sketchcord/tree/main)


and below to deploy on Railway


[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template/Cv0lHp?referralCode=S2-ghV)


To deploy locally, see [Contributing guide](https://github.com/nicesapien-too/SketchCord#contributing)

### Example
```bash
curl -X POST https://sketchcord.vercel.app/api/send -H "Content-Type: application/json" -d "{\"url\":\"https://discord.com/api/webhooks/980005854130630726/ZCRSROTTWRBF1UfLpbpljXsWudc8AUbBNVK0UMAQNnoLgu9IW-a0Ux0hahpyL7ynkCmi\",\"content\":\"Woof-woof\",\"avatar_url\":\"https://i.imgur.com/oBPXx0D.png\",\"username\":\"Wolf\",\"embed_color\":\"#FFFFFF\",\"embed_description\":\"Hey @everyone. Look its working\",\"embed_footer\":\"Powered by SketchCord\",\"embed_img_url\":\"https://i.imgur.com/ZGPxFN2.jpg\",\"embed_title\":\"Look, its working\",\"embed_timestamp\":\"2022-05-30T05:00:00.000Z\",\"tts\":\"false\"}"
```
Don't forget to replace `url` with your webhook URL!
## Using
First, before we get started, Let me tell you the basic setup.
First you will need to add a `content-type` header with `application/json` value.
Then you will have to write json in Request body to specify your message.
Make sure to send a POST request only.
Here are the available body params(all should be declared as strings in json):


| Name        | Value       | Required    |
| ----------- | ----------- | ----------- |
| content      | Main message       | `embed_title` or this|
| username   | Username of  webhook      | false |
| avatar_url | Avatar URL of embed. Useful if using same webhook for several jobs. | false |
| url | URL of Discord webhook | true |
| tts | Sends message in Text-to-speech if enabled on user device. Set either true or false| true |
| embed_title | Title of webhook. Required if you want a embed | `content` or this|
| embed_color | Color of embed in Hex | false |
| embed_description | Long description of embed | false |
| embed_url | When embed_title is clicked, this link will open. This is URL of embed. | false |
| embed_img_url | URL of the image used in Embed. | false |
| embed_footer | A short message displayed at bottom of Embed. | false |
| embed_timestamp | Timestamp of embed. Changes according to timezone. Eg. `2022-05-30T05:00:00.000Z` | false |


And that's how it works. Currently, you can only add one embed per message and zero fields per embed.
## Contributing
First clone the repository locally, make sure NodeJS is installed on your machine.
Then run:
```cmd
$ npm install
```
To build website, run:
```cmd
$ npm start
```
or
```cmd
$ node .
```
Then test it by sending a request to http://localhost:3311/api/send
