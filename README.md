Cache, Proxies, Queues
=========================

### Setup

* Clone this repo, run `npm install`.
* Install redis and run on localhost:6379

There are three files, main3000.js, main3001.js and proxy.js.

#### Complete set/get for an expiring cache

The /set route is used for setting a key in redis with the value "this message will self-destruct in 10 seconds". After the key has been set, the value persists for 10 seconds and can be retrieved using the /get route.

#### Complete recent

If we run main.js on port 3000, then localhost:3000/recent displays a list of 5 recently visited sites.

#### Complete upload/meow

The following curl command is used to upload image from the command line.

```
curl -F "image=@./img/morning.jpg" localhost:3000/upload
```

The method /upload saves this image in a queue. The method /meow pops it from the queue and displays on localhost:3000/meow.

#### Additional service instance

An additional instance can be run using the following command:
```
 main3001.js.
```

#### Demonstrate proxy

The file proxy.js creates a proxy server that listens on port 3002 and uniformly delivers requests to the ports 3000 and 3001.

#### Screencast
[Demo](https://youtu.be/vnaphFaUBaE)
