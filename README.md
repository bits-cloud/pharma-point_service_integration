# Pharma-Point Service Integration
Pharma-Point has the possibility to integrate 3rd Party Services into it's UI.

When an external site is launched, the window will close itself after 5 Minutes of inactivity. You are responsible, to extend the timeout while the user is still active.

Every window will clear the old browsing data when it's opened. But it is possible some error prevents clearing the data.
Whenever possible, use an anonymous mode within Pharma-Point.

You can generate an OpenAPI 3.1 Client with the provided openapi.json file.
The api listens by default on http://127.0.0.1:8080, which is callable from within your webview window.

## How to Determine if the website is running within Pharma-Point:
- window.__APPLICATION_NAME__ is set and contains PHARMA-POINT
- window.isPharmaPoint = true
- window.pharmaPointApiEndpoint container the ip + port of the API

## Create a smooth customer journey:
- while the user is active (presses buttons), send requests to the "extend_timeout" endpoint, to extend the 5 minute timeout
- when the customer is finished, send a request to close the window