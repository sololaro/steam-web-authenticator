# steam-web-authenticator
Nodejs server for generating steam codes

# Usage
- Do the ``` npm install ```

- Copy file config.sample.js to config.js and edit it
```javascript
    
module.exports = {
	username: "user",
	password: "pass",
	steamusername: "user",
	steampassword: "pass",
	identity_secret: "",
	shared_secret: "",
	port: 21377
}
```
  - **username** and **password** will be used for authenticating using HTTP basic auth.
  - **shared_secret** is your shared_secret steam guard code. If you don't know what shared_secret is or where to get it, try [here](http://goo.gl/search/steam+shared_secret)
  - **identity_secret** its identity_secret for steam guard, used for accepting confirmations.
  - **steamusername** and **steampassword** these are your steam login credentials. For now they are stored unencrypted in config file, probably in future i will do smh about it
  - **Port** is the number you want your web server going on

- Do the ```npm run``` or ```node index.js```
- If everything went correct, you can now launch browser and enter your IP address with selected port
- Path ```/``` is main page where code is refreshed with ajax every 1 sec. Path ```/raw``` can be used for API's etc. It returns you only key, but you have to refresh manually. You need to authenticate for both of the pages 
# FAQ
## Code is wrong
That probably means your secret is wrong. I am not able to check whether your secret is valid
## Running it on domain/subdomain
You need reverse proxy for that, [google is your help](http://goo.gl/search/running+reverse+proxy+for+nodejs)
## Disabling authentication
For now it is not possible, you can try removing it by yourself from the code
```diff
- Please note that this is very very very early version and I cannot guarantee you full security.*
```
