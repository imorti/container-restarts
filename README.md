This project is to demonstrate different ways to set containers to run using the Docker Restart Policy. 

Run:

```docker build -t test-restart .```

Then: 

```docker run --name testing-restarts testing-restart```

Then run this on repeat until you see the container has exited (10 seconds):

```docker ps -a```

Clearly we can see the container stops running. But if we run it with this: 

```docker run --name testing-restarts --restart always testing-restart ```

We see after 10 seconds the container fails then runs again because docker restarted it. 

However, if you want to just have it restart unless you have a real problem better to run with this; 

```docker run --name testing-restarts --restart unless-stopped testing-restart```



Much thanks to @madflojo for this article: 
https://blog.codeship.com/ensuring-containers-are-always-running-with-dockers-restart-policy/