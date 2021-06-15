# Make Chat

## I'm Ready to Get Started

1. Build out a basic view
    - Install/integrate dependencies
    - Implement a basic, index view
2. Integrate sockets
3. Implement user form
4. Style and send messages
5. Connect/disconnect users
6. Create/persist/join channels

You know the drill by now. But in case you've forgotten the Node essentials...

Create your project directory. Make sure to speicfy app.js as your entry point in the `npm init` setup!

```bash
$ mkdir your-project-name
$ cd your-project-name
$ npm init
```

When your `package.json` arrives, do yourself a favor and make sure it has the `express`, `mongoose`, and `express-handlebars` module dependencies installed. Also, create an `app.js` while you're at it.

Install dependencies and create `app.js`

```bash
$ npm install express mongoose express-handlebars socket.io --s
$ touch app.js
```

Now copy the following code into `app.js`:

```js
//App.js
const express = require('express');
const app = express();
//Socket.io has to use the http server
const server = require('http').Server(app);

//Express View Engine for Handlebars
const exphbs  = require('express-handlebars');
app.engine('handlebars', exphbs());
app.set('view engine', 'handlebars');

app.get('/', (req, res) => {
  res.render('index.handlebars');
})

server.listen('3000', () => {
  console.log('Server listening on Port 3000');
})
```
### Add in the views

Try running the server using `nodemon`. you'll notice you haven't yet created `index.handlebars`.

Let's do that.

Set up your initial /views

```bash
$ mkdir views
$ cd views
$ touch index.handlebars
$ cd ..
```

Copy the following into `/views/index.handlebars`

```handlebars
<!--index.handlebars-->
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
  </head>
  <body>
    <h1>Socket.io</h1>
  </body>
</html>
```
##### Go commit!

### Looking Pretty Good!
Time to put on your big kid gear, because you're now about to make your first websocket connection!

[PREVIOUST](./1/README.md)                   <br>      [NEXT](./3/README.md)
