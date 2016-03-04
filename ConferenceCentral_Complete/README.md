App Engine application for the Udacity training course.

## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]


## Design Choices
1. Task 1: Add Sessions to a Conference
	Created a Session class with the following parameters: name, conferenceId, highlights, speaker, duration, typeOfSpeaker, date and startTime. As there is a speaker associated with every session, speaker is added as one of the Session parameters. If in future, there are multiple speakers associated with a session, then this can be extended to a list. Also, if in future, a speaker is associated with multiple sessions, then a Speaker class can be created to avoid storing the same speaker with different sessions.

	getConferenceSessions: implemented a query of Session kind that compares the given conference with the conferenceId and returns all the sessions.

	getConferenceSessionsByType: implemented a query of Session kind that compares the given conference and type, and it returns all the Sessions associated with that conference.

	getSessionsBySpeaker: implemented a query of kind Session that compares the speaker property with the speaker provided by the user and returns all the sessions given by that speaker.

2.  Task 2: Add Sessions to User Wishlist
	Added a list (sessionKeysInWishList) of Session keys in the Profile class. This field stores the user's sessions wishlist. As user's profile already contains all the data associated with the user, I believe adding a new list and storing the wishlist sessions within the profile is the best place to manage this wishlist.


## Task 3
Two additional queries
1. getSessionsByDay: list all sessions which are scheduled on the given day.
2. getSessionsByDuration: list all sessions which are scheduled between the given minimum and maximum duration.

## Task 4
A user might only be able to attend the conference on a particular day and would like to see all the sessions scheduled on a particular day of the conference. getSessionsByDay query solves this problem and returns all the sessions scheduled on a particular day of the conference.

A user is only interested in attending a few sessions which are scheduled for not more than 2 hours. getSessionsByDuration query will return the sessions which are scheduled between the given duration.


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
