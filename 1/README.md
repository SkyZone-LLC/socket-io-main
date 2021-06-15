# Make Chat

## HTML5 Bidirectional Communication => WebSocket

Before we jump into building with websockets, lets take a second to look at where the WebSocket standard came from and how it works. Much of this complexity is buried into the libraries and tools we use, so lets take a minute to look at them.

As HTML5 was being developed, it became clear that the web needed a bidirectional full-duplex standard to allow for bidirectional communication. A new standard called WebSocket was recommended in June of 2008 by Michael Carter—an influential HTML5 game developer.

In February 2010, Google (being a champion of HTML5) made Chrome 4 the first browser to ship a full support of the standard and enabled by default with Safari 5.0.0 in a close second. The last was Internet Explorer 10 in December 2011.

The WebSocket standard begins with an HTTP handshake, but then switches to the WebSocket standard that does not conform to the HTTP protocol.

![Image of socket](./image.png)

Here's an example of how the request for the handshake and the server's response looks:

```bash
GET /chat HTTP/1.1
Host: server.example.com
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: x3JJHMbDL1EzLkh9GBhXDw==
Sec-WebSocket-Protocol: chat, superchat
Sec-WebSocket-Version: 13
Origin: http://example.com
```

Server response:
```bash
HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: HSmrc0sMlYUkAGmm5OPpG2HaGWk=
Sec-WebSocket-Protocol: chat
```

The request sends a `Sec-WebSocket-Key` which contains base64-encoded random bytes, and response responds with with a hash of the key in the `Sec-WebSocket-Accept` attribute which prevents resending old messages. This key/hash pattern does not provide any authentication, privacy, or integrity. WebSocket has unique security and privacy concerns.

For more information read this [WebSocket documentation](https://hpbn.co/websocket/).

## What We are Going to Build

### User Stories

- Upon entering the application, I can choose a username to go by.
- I can enter a message that shows up on all clients.
- I can join / create chat channels.
- I will never have to refresh the page to receive new messages.
- I can start a private message with another user. (Stretch Challenge)

### Wireframe

Let's look at a simple wireframe of what we want to build. Basically it is a chat application with very little underutilized space.
![Image of socket](./wireframe.png)

## This sounds impossible...

And it certainly would be next to impossible... if it weren't for a little library called socket.io!

Socket.io is a lightweight wrapper you can use to implement websockets using the WebSocket standard.

*Remember that Socket.io has both a server and a client side to handle both the sending and receiving of websocket messages.*


Some types of applications that use socket.io are the following:

- Live Messaging / Chat Rooms
- Realtime Data Analytics
- Multiplayer Games such as Agar.io or Slither.io
- Applications you make after this tutorial (hopefully)

Lastly, before we get started, a friendly reminder:
### Using Git/GitHub

As you go through this tutorial, you will also be making commits after completing milestones. This is a requirement, you must make a commit whenever the tutorial prompts you. This not only further enforces best practices for software engineering, but also will help you more easily figure out where a bug originated from if you break your progress up into discrete, trackable chunks.

When prompted to commit, you'll see a sample commit message. Feel free to use your own message, so long as it clearly and concisely covers the work done.

Lastly, the commit prompts in this tutorial should be the minimum amount of times you commit. If you want to do more commits, breaking your chunks into even smaller chunks, that is totally fine!

[NEXT](./2/README.md)