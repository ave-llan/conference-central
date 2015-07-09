App Engine application for the Udacity training course.

## Products
- [App Engine][1]

## Language
- [Python][2]

## APIs
- [Google Cloud Endpoints][3]

# Design Choices

### Sessions
Session objects are children of conference objects and can be created by the organizer of the conference. 

Speakers at sessions must be registered users with a Profile just like attendees, so  `Session.speaker` simply points to a user_id. Just like Conferences, Sessions have a `maxAttendees` property and a `seatsAvailable` count which decrements as attendees register for the session.


### Profile
Conference attendees, speakers, and organizers are all register using the same Profile object. 
In addition to the descriptive properties of `displayName`, `mainEmail`, and `teeShirtSize`, Profile objects have links to conferences and sessions: `conferenceKeysToAttend` and `sessionsKeysToAttend`.


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
