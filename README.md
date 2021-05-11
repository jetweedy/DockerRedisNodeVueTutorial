# Redis, Websockets, Node and Vue.js

Using the following tutorial:

https://redislabs.com/blog/how-to-create-notification-services-with-redis-websockets-and-vue-js/

Redis Publish Subscribe Tutorial:

https://www.tutorialspoint.com/redis/redis_pub_sub.htm


## Installation

1. Install Docker, Node and Nodemon:
1. Pick a directory to start from, and then run each of these blocks in separate windows:

### Run Redis in docker
```
docker run -it --rm --name redis-server -p 6379:6379 redis
```

### Run a Node server
```
mkdir notifications
cd notifications
mkdir notif-server
cd notif-server
npm init -y
npm install ws redis
```
```
nodemon server.js
```

### Run the front-end client (how over-engineered!)
```
cd notifications
npm install -g @vue/cli
vue create webclient
cd webclient
npm install bootstrap-vue bootstrap
```
```
npm run serve
```

### Manually send some messages from Redis:
```
docker exec -it redis-server redis-cli
127.0.0.1:6379> PUBLISH app:notifications  "message from Redis2"
```