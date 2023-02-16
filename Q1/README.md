to start the container,
locate to Q1 directory and then execute the following:

```
docker build -t q1 .
docker run -p 8080:80 -d q1
```

your frontend is now available at port 8080 of your system.


## problems:

when we changed the defaults.conf config file while attached to the container and then execute
```
service reload nginx
```

or
```
nginx -s reload
```

the new configuration changes didn't apply and the container needed to be restarted.