[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/rustyio/grimace)

# Grimace - Tap Into IMAP

Grimace is an open-source microservice for tapping into IMAP.
Conceptually, it is very simple:

* Connect to an IMAP account on your user's behalf.
* Wait for a new email message.
* Trigger a webhook with the contents of the message.
* **Scale to tens of thousands of users.**

We at [FiveStreet](http://www.fivestreet.com) wrote Grimace to solve
scaling issues as we grew by over 60x in volume over the past year.

## Data Model

Grimace has:

* **Partner** - One entry per app / environment.
* **User** - An application's user. Holds user-specific credentials.
* **Partner Connection** - Holds application-specific credentials.
* **Connection Type** - Configures an authentication transport
  mechanism. For example, there are connection types for "Gmail OAuth
  1.0" and "Gmail OAuth 2.0".

## Security

If you use this code, *PLEASE* ensure that you safeguard your
passwords, and preferably, make sure your data is encrypted at
rest. It is a big responsibility to hold the keys to someone's
email. Treat it with the appropriate amount of caution.

## Development

## Production

Run:

    foreman s -f Procfile

# Testing

Run:

    rake test:all

# Stress Testing



Run:

    script/stress-test
