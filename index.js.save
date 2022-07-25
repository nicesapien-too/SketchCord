const express = require('express')
const app = express()
const PORT = 3311
const axios = require('axios');
app.use(express.static('public'));
app.use(express.json())
// Function for converting hex color code to decimal.
function hexToDecimal(hex) {
	return parseInt(hex.replace("#", ""), 16)
}
// This API is made with ExpressJS
app.set('x-powered-by', false);
// Starting
app.post('/api/send', function(req, res, next) {
	res.set('made-by', 'NiceSapien')
		var webhook_url = req.body['url'];
		var message = req.body['content'];
		var username = req.body['username'];
		var color = req.body['embed_color'];
		var title = req.body['embed_title'];
		var description = req.body['embed_description'];
		var url = req.body['embed_url'];
		var embed_img = req.body['embed_img_url'];
		var footer = req.body['embed_footer'];
		var footer_icon = req.body['embed_footer_icon'];
		var timestamp = req.body['embed_timestamp'];
		var is_tts = req.body['tts'];
		var avatar_url = req.body['avatar_url']
		// Converting string to boolean
		var tts = (is_tts.toLowerCase() === 'true');
		// Checking if webhook URL is given. If not, then block user from sending message and ask for URL.
	if (!webhook_url == "") {
	try {
	  // Check if there is a embed title. If there is, it will add embed otherwise it will not.
	  if (!title == "") {
	    //sending http request to Discord API with axios
		axios
			.post(webhook_url, {
				content: message,
				username: username,
				avatar_url: avatar_url,
				tts: tts,
				embeds: [{
					title: title,
					color: hexToDecimal(color),
					description: description,
					url: url,
					timestamp: timestamp,
					image: {
						url: embed_img,
					},
					footer: {
						text: footer,
						icon_url: footer_icon,
					}
				}],
			})
			.then(res => {
			  // Sending response
				console.log(`statusode: ${res.status}`);
				console.log(res);
				res.status(200).send(res);
				
			})
			.catch(error => {
			  // Sending error if found any
				console.error(error);
				res.send(error)
			});
	  } else {
	    //This code will be executed if there is no embed title.
	    axios

			.post(webhook_url, {

				content: message,
				username: username,
				tts: tts,
			})
						.then(res => {

			  

				console.log(`statusode: ${res.status}`);
				console.log(res);
				res.status(200).send(res);
				
			})
			.catch(error => {
				console.error(error);
				res.send(error)
			});
	  }

	} catch (err) {
		res.set('error', err.message)
	}} else {
	  // Show a error if thete is no webhook URL
	  res.status(404).send("Please provide a webhook URL.");
	}
});
app.listen(process.env.PORT || PORT, () => console.log(`Server listening on port: ${PORT}`));
