# 24-7_hosting_with_replit
How do I get free 24/7 hosting with replit? Here's how.

> This only works for node.js/html, css, javascript repls.

## Creating a Replit
Assuming you've already creating a replit account, let's make a repl:

1. Go to https://replit.com/~
2. Create a *repl* by clicking the ➕ sign under the 'Create' section:
![](https://user-images.githubusercontent.com/69215413/146983219-89cfbaae-c309-4f20-8ef1-b53143c8284d.png)
3. Select Node.JS as your template (or HTML, CSS, JavaScript for a website):
![](https://user-images.githubusercontent.com/69215413/146983331-73da02f0-b3de-4481-9dec-5693f461c9a7.png)
4. Give it a name, or stick with the one that is auto generated:
![image](https://user-images.githubusercontent.com/69215413/146983436-9a3fc61d-9ce5-4d8e-bfac-007afb001f43.png)
5. Click "Create Repl":
![](https://user-images.githubusercontent.com/69215413/146983645-2bb54241-6ba9-49d1-a2ad-1c84e63f96ec.png)

## Hosting

### Install Packages
Run this in the Shell:
```sh-session
npm install express ping-monitor
```

⚠️ It is very important that you use the Shell tab for this:
![image](https://user-images.githubusercontent.com/69215413/146984572-12a1fad9-b007-4c6b-bfa0-feaff4e8757b.png)

If you are on mobile, then you probably won't see the tab, in that case go into "View Desktop Mode". Learn how below:
- for Android [click here](https://www.techadvisor.com/how-to/google-android/view-desktop-websites-android-3791327/#:~:text=On%20your%20Android%20device%2C%20open,revert%20to%20the%20desktop%20version.)
- for iOS (iPhone) [click here](https://browserhow.com/how-to-request-and-view-desktop-site-on-safari-ios-ipados/)

### index.js
Put this code in your `index.js` file for the node.js template, or `script.js` for the HTML, JavaScript, CSS repl template:
```js
const keepAlive = require('./server');
const Monitor = require('ping-monitor');

keepAlive();
const monitor = new Monitor({
    website: '',
    title: 'NAME',
    interval: 2 // minutes
});

monitor.on('up', (res) => console.log(`${res.website} its on.`));
monitor.on('down', (res) => console.log(`${res.website} it has died - ${res.statusMessage}`));
monitor.on('stop', (website) => console.log(`${website} has stopped.`) );
monitor.on('error', (error) => console.log(error));
```
