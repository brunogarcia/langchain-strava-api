# LangChain, OpenAI and Strava API

The main goal of this project is to research about the LangChain library and the API of OpenAI using the Strava API.

## Requirements

- You must have a OpenAPI key
  - https://platform.openai.com/account/api-keys
- You must have an account on Strava
  - https://www.strava.com
- You must create an app on Strava
  - https://www.strava.com/settings/api

## Documentation

- Strava API
  - https://developers.strava.com/docs/reference/
- Strava Auth
  - https://developers.strava.com/docs/getting-started/
- Strava Playground
  - https://developers.strava.com/playground/

## How to get a valid token from Strava?

Paste the URL into the browser window and hit enter.
Remember to update the value of YOUR_CLIENT.

```bash
http://www.strava.com/oauth/authorize?client_id=YOUR_CLIENT_ID&response_type=code&redirect_uri=http://localhost/exchange_token&approval_prompt=force&scope=activity:read_all
```

When you see the authorization page, click “Authorize”

After you click “Authorize,” you should see something like, “this site can’t be reached”

Stay on that page and look at the URL

The URL will show the authorization code and scope accepted by the athlete

Copy the authorization code

Make a cURL request to exchange the authorization code and scope for a refresh token, access token, and access token expiration date

```bash
curl -X POST https://www.strava.com/oauth/token \
-F client_id=YOUR_CLIENT_ID \
-F client_secret=YOUR_CLIENT_SECRET \
-F code=AUTHORIZATION_CODE \
-F grant_type=authorization_code
```
