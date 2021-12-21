# 24/7 Free Hosting with Repl.it
How do I get free 24/7 hosting with replit? Here's how.

*If this repository helps you in any way, give it a* :star:\:\
![](https://user-images.githubusercontent.com/69215413/146993173-a8bede48-c001-4028-bf77-626113d599a6.png)

> :warning: **Warning:** This only works for `Node.JS` or `HTML, CSS, JS` repls.
## Index
- [Creating a Repl](#creating-a-repl)
- [Hosting](#hosting)
    - [Install Packages](#install-packages)
    - [index.js](#indexjs)
    - [server.js](#serverjs)
    - [Run It](#run-it)
    - [UptimeRobot](#uptimerobot)
    - [Profit](#profit)

## Creating a Repl
Assuming you've already [created a replit account](https://replit.com/signup), let's make a repl:
> 💡 **Tip:** If you already have a repl, go to the [next section](#hosting).

1. Go to [replit.com/~](https://replit.com/~)
2. Create a *repl* by clicking the ➕ sign under the 'Create' section:\
![](https://user-images.githubusercontent.com/69215413/146983219-89cfbaae-c309-4f20-8ef1-b53143c8284d.png)
3. Select Node.JS as your template *(or HTML, CSS, JS for a site)*:\
![](https://user-images.githubusercontent.com/69215413/146983331-73da02f0-b3de-4481-9dec-5693f461c9a7.png)
> For Node.JS 16+, fork [this repl](https://replit.com/@piemadd/Node-1661) instead of creating a new one!
4. Give it a name, or stick with the one that is auto generated:\
![](https://user-images.githubusercontent.com/69215413/146983436-9a3fc61d-9ce5-4d8e-bfac-007afb001f43.png)
5. Click "Create Repl":\
![](https://user-images.githubusercontent.com/69215413/146983645-2bb54241-6ba9-49d1-a2ad-1c84e63f96ec.png)

## Hosting
### Install Packages
1. Run `npm init` in the Shell
2. Run this in the Shell to install the dependencies:
```sh-session
npm install express ping-monitor
```

⚠️ **Warning:** It is very important that you **use the Shell tab** for this:

![](https://user-images.githubusercontent.com/69215413/146991197-2e6ae207-942d-473f-ad1e-6cb78067cef8.png)

**If you are on mobile, then you probably won't see the Shell tab**, in that case, go into "View Desktop Mode". Learn how below:
- for Android [click here](https://www.techadvisor.com/how-to/google-android/view-desktop-websites-android-3791327/#:~:text=On%20your%20Android%20device%2C%20open,revert%20to%20the%20desktop%20version.)
- for iOS (iPhone) [click here](https://browserhow.com/how-to-request-and-view-desktop-site-on-safari-ios-ipados/)

After that, you should be able to access Shell as normal. When you are done using the Shell, I recommend going back to regular view, as the sizing of the page gets a bit weird on Desktop mode.

### index.js
Put this code in your `index.js` file for the Node.JS template, or `script.js` for the HTML, CSS, JS template:
```js
const keepAlive = require('./server');
const Monitor = require('ping-monitor');

keepAlive();
const monitor = new Monitor({
    website: '',
    title: 'NAME',
    interval: 2
});

monitor.on('up', (res) => console.log(`${res.website} its on.`));
monitor.on('down', (res) => console.log(`${res.website} it has died - ${res.statusMessage}`));
monitor.on('stop', (website) => console.log(`${website} has stopped.`) );
monitor.on('error', (error) => console.log(error));
```
> 💡 **Tip:** If you already have code in your `index.js` file, just put this code at the bottom of the code, or where ever you feel it looks best.

### server.js
1. Create a file called `server.js`:\
![](https://user-images.githubusercontent.com/69215413/146991492-2b9714dc-23d7-4d98-a932-57283a91b9cd.png)\
![](https://user-images.githubusercontent.com/69215413/146991520-d795f4d9-21ab-4014-a685-5007fb44d96d.png)

2. Paste-in this code:
```js
const express = require('express');
const server = express();

server.all('/', (req, res) => {
    res.send('<h2>Server is ready!</h2>');
});

module.exports = () => {
    server.listen(4000, () => {
        console.log('Server Ready.');
    });
    return true;
}
```
> 💡 **Tip:** See where I put 4000, it is recommended you change that if you are using multiple repls. For example, you can do 1000, 2000, 3000, or whatever else. This is just a port.

### Run It
Click the 'Run' button:\
![](https://user-images.githubusercontent.com/69215413/146987397-637e9f1a-2987-459b-86ef-bc651ca525be.png)

### UptimeRobot
We will be using [UptimeRobot](https://uptimerobot.com/) as the monitoring system.

1. Copy the URL of the website that shows when you run the repl. If you are on mobile, this will be on the "Output" tab; on Desktop, you'll see it in the upper right corner of your screen:
![](https://user-images.githubusercontent.com/69215413/146987775-56f77514-c7c1-4a67-8d81-7de17200d99b.png)
2. Go to [uptimerobot.com](https://uptimerobot.com/) and create a new account:\
![](https://user-images.githubusercontent.com/69215413/146987913-f3fdd1b7-c2e0-4f2b-8bf0-246310c11209.png)\
![](https://user-images.githubusercontent.com/69215413/146988111-d8c10c44-5ea7-4926-a404-024a9ae88bee.png)\
*Don't forget to check your email!*
3. After clicking the link in your email, it should take you to the [dashboard](https://uptimerobot.com/dashboard#mainDashboard). Here, you can create a new monitor:\
![](https://user-images.githubusercontent.com/69215413/146988709-752cb7fd-0419-4097-90cf-c065607fce98.png)
4. Select these settings, then save (you'll need to double click the "Create Monitor" button):\
![](https://user-images.githubusercontent.com/69215413/146994547-724773fb-a1fd-4f85-b325-4e070cb4dd99.png)\
"https://replname.yourusername.repl.co" should be replaced with the URL we copied from our repl earlier.

### Profit
Run your repl, and now your bot/website/project will be hosted 24/7. Note that this is free hosting, so obviously it isn't perfect. But it is certainly good enough to experiment with!\
Good luck and have fun building your project.

*pssst: If you need any help or want to chat with fellow developers join our [Discord Server](https://discord.gg/Ujn7MJDTeq)* ✨
