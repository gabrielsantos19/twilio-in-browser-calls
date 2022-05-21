# twilio-in-browser-calls on a docker container

1. Build the container. Inside the folder with the Dockerfile, run:
```
docker build -t twilio .
```


2. To start a container you can use the following command:
```
docker run -d -p 3000:3000 -e 'TWILIO_ACCOUNT_SID=' -e 'TWILIO_AUTH_TOKEN=' -e 'TWILIO_API_KEY_SID=' -e 'TWILIO_API_KEY_SECRET=' -e 'TWIML_APP_SID=' -e 'TWILIO_NUMBER=' -e 'NGROK_AUTHTOKEN=' twilio:latest
```
- Add the variables from your Twilio account in the appropriate place.
- The TWILIO_NUMBER must include the + signal. eg.: +10000000007
- Get your Ngrok authtoken and place it in NGROK_AUTHTOKEN.


3. Get the Ngrok url. 
```
docker logs <the container id>
```
Search for a line with ***msg="started tunnel"*** in it. The url at the end is your Ngrok url.


4. Set up your Phone Number. Go to Twilio > Phone Numbers > Active numbers > ***your_number***. Then, in Voice & Fax section, set CONFIGURE WITH to TwiML App and set TWIML APP to the appropriate app.


5. Set up you App. Go to Twilio > Phone Numbers > TwiML apps > ***your_app***. Then, in Voice section, set REQUEST URL to <your_ngrok_url>/handle_calls .


6. Go to <your_ngrok_url> and check out the app.
