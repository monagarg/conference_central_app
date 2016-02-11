App Engine application for the Udacity training course.

## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]


## Design Choices
1. Task 1: Add Sessions to a Conference
	Created a Session class with the following parameters: name, conferenceId, highlights, speaker, duration, typeOfSpeaker, date and startTime. The conferenceId parameter contains the webSafeKey for the conference to which the session belongs.

	getConferenceSessions: implemented a query of Session kind that compares the given conference with the conferenceId and returns all the sessions.

	getConferenceSessionsByType: implemented a query of kind session that compares the given conference with the conferenceId and return all the Sessions associated with that conference. After that, created a filter that filters the sessions based on the Type provided by the user.

	getSessionsBySpeaker: implemented a query of Session kind that compares the speaker property with the speaker provided by the user and returns all the sessions give by that speaker.

2.  Task 2: Add Sessions to User Wishlist
	Created a WishList class which contains userId (email id of the user) and sessionId (webSafeKey of the session).

	getSessionsInWishlist: created a query to obtain all the wishlists for the logged-in user using the ancestor query. And then created a query to obtain the session objects from the wishlists and returned all the sessions that the user is interested in.



## Setup Instructions
1. Update the value of `application` in `app.yaml` to the app ID you
   have registered in the App Engine admin console and would like to use to host
   your instance of this sample.
1. Update the values at the top of `settings.py` to
   reflect the respective client IDs you have registered in the
   [Developer Console][4].
1. Update the value of CLIENT_ID in `static/js/app.js` to the Web client ID
1. (Optional) Mark the configuration files as unchanged as follows:
   `$ git update-index --assume-unchanged app.yaml settings.py static/js/app.js`
1. Run the app with the devserver using `dev_appserver.py DIR`, and ensure it's running by visiting your local server's address (by default [localhost:8080][5].)
1. (Optional) Generate your client library(ies) with [the endpoints tool][6].
1. Deploy your application.


[1]: https://developers.google.com/appengine
[2]: http://python.org
[3]: https://developers.google.com/appengine/docs/python/endpoints/
[4]: https://console.developers.google.com/
[5]: https://localhost:8080/
[6]: https://developers.google.com/appengine/docs/python/endpoints/endpoints_tool
