# twilio-in-browser-calls on a docker container

Build the container.
Inside the folder with the Dockerfile, run:

```
docker build -t twilio .
```

To start a container you can use the following command:


```
docker run -it --rm -p 3000:3000 -e 'TWILIO_ACCOUNT_SID=' -e 'TWILIO_AUTH_TOKEN=' -e 'TWILIO_API_KEY_SID=' -e 'TWILIO_API_KEY_SECRET=' -e 'TWIML_APP_SID=' -e 'TWILIO_NUMBER=' twilio:latest
```

*ADD THE VARIABLES FROM YOUR ACCOUNT IN THE APPROPRIATE PLACE.

*e.g.: Get you Twilio account SID and add it to the variable so it looks like TWILIO_ACCOUNT_SID=5184651safd4dfs.


Then, check out http://127.0.0.1:3000/
