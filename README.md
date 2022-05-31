# SketchCord
**Sketchcord** is used to send messages to **Discord** using Discord **Webhooks** by sending **http requests**. It is an unofficial (REST)API. Works great with **Sketchware**/Sketchware Pro/ Sketchware Revolution or Sketchware Gold.
## Hosting
To use it, you can use the default API, **https://sketchcord.heroku.app/api/send**. But If your app is too popular, you can host the API yourself. Just click the below button.
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/nicesapien-too/sketchcord/tree/main)
## Using
First, before we get started, Let me tell you the basic setup.
First you will need to add a `content-type` header with `application/json` value.
Then you will have to write json in Request body to specify your message.
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

