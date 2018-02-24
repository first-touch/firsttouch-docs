# Errors

In FirstTouch we use a concept of Endpoint where all the generic error codes are
defined.
These are the errors that the API might produce:


Error Code | Meaning
---------- | -------
422 | Unprocesseable entity -- Your request is invalid.
401 | Unauthorized -- Your API key does not allow you to perform this action.
404 | Not Found -- The specified resource could not be found.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
