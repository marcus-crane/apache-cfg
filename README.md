# Apache Configurations
### So you wanna run both Node applications and static files on Apache, huh?
##### It doesn't have to just be Node really. Anything works but I just happen to have used that with this.

### EDIT: I was going to do detailed explainations in the pull request but I've decided (at some point), a gitbook would be more suitable. I've got the basic layout up [here](https://github.com/marcus-crane/server-cfg)

I can't say this is best practice (since I have no idea what that even is, but here's how I was doing it until very recently (like, today because I'm gonna try out nginx next)

As the note says above, fully detailed explainations of what each line does is sitting in the pull request above. There will also be some notes in the files themselves which can be ignored should you use them. Just don't copy them or delete them if you do.

### I hate reading! Give me a table to quickly glance at showing what file I should copy

The point of these is that they're all being served from one single IP address and from one single server.

| I want to serve up        |           Filename           |
| ------------------------- | ---------------------------- |
| A single static site      | single-static-site.conf      |
| A single server           | port-forward-fun.conf        |
| Multiple static sites     | duplicate-static-disco.conf  |
| Multiple servers          | super-server-surprise.conf   |
| A mix of static + servers | mixed-up-mayhem.conf         |
| A mix but with SSL enabled| secure-me-up-scotty.conf     |
| SSL while disabling http  | disable-dastardly-http.conf  |


### I just want to serve up a single static folder to Port 80

Sure! You probably actually don't need a VirtualHost file at all but it's an easy enough stepping stone to show how that works actually.

Check out **single-static-site.conf**

### I want to run a Node server on Port 80!

Noooo, for reasons beyond my current understanding, you should never just straight up bind to Port 80. Firstly, it requires root permissions anyway. I assume just to stop people randomly binding to Port 80 and messing up other peoples stuff

Anyway, what you should try instead is running your application on some other port then forwarding it to Port 80.

Check out **port-forward-fun.conf**

### I want to serve up multiple static files but how can I get both if there's only one Port 80?!

This is gonna be some more port forwarding fun!

Check out **duplicate-static-disco.conf**

### Multiple servers?

You got it! Have a peek into **super-server-surprise.conf**

### How about a mix of Node servers **AND** static sites?

No prob, check out **mixed-up-mayhem.conf**

### Ok, friend. I'm ready for the big time. What does SSL (https://) look like

Aww yeah. You're ready for **secure-me-up-scotty.conf**

### So, I've got SSL (https://) set up but now I have two versions (http:// and https://)! How do I force/redirect to https:// only?

We're at the home stretch (unless I've written more)

You're after **disable-dastardly-http.conf**

### Got any more names?

Nah

### Hey, a thing you did was wrong?

Oh, probably. Feel free to submit an issue!
