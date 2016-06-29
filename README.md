# NetCat-Hello-world
 netcat  is  a simple unix utility which reads and writes data across network connections, using TCP or UDP protocol.
 Uses of NetCat

**Creating a Chat Server**

For lisener ,type
```
nc -lp <port>
```
For the client type
```
nc <IP ADDRESS > <PORT>
```
**Web Server**

In your basic html file like this
> $ cat index.html
```
<html>
  <head>
    <title>
      Hello
    </title>
  </head>
  <body>
    <h2>
      Hello Reegan Reader zilogic systems in reegan
    </h2>
  </body>
</html>
```

Run basic static web page

```
nc -lp <PORT> -q 1 < index.html
```

for examle:

> nc -lp 1234 -q 1 index.html

Now open your favourite browser

https://localhost:1234

or
```
 https://<IP Address>:1234
```

Note:
Now open url in browser, and reload web page `cannot find the page` because netcat stops successfully after sending the contents of the HTML file
So make a while loop

> while true; do nc -l 1234 -q 1 < index.html; done

**File transfer**

_Transfer_

```
nc -lp 1234 < index.html
```
Note:

 It is same a logic of the chat server.
  use -k for server stops or user stop chatting to intimate in terminal
   > nc -k -lp 1234

_Receiver_

nc  <IP Address> <PORT> >  receiver_index.html

**Getting remote shell**

When you share your terminal in remotely use this
```
nc -lp <PORT> -e /bin/bash
```
To access remote shell
```
nc <IP ADDRESS> <PORT>
```
**Port Scanning**
```
nc -v -z -w <SEC> <IP ADDRESS> < PORT RANGE: 1 -100>
```
