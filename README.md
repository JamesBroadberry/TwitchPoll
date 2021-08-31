# TwitchPoll

A HTML Twitch Overlay that reads chat of a Twitch account and displays chat's single words as votes recorded in the last five minutes.

# Hosted on GitHub pages

https://jamesbroadberry.github.io/TwitchPoll/

# How it works

- Upon load, the page anonymously connects to the user's twitch chat
- It keeps track of each user's latest message which was just a single word (their vote)
- Every time the UI refreshes, every user's votes are grouped and then ordered from highest to lowest, discarding any which are older than 5 minutes and displayed on the page.

Doing it like this allows chatters to change their vote by sending another message of just a single word but doesn't stop them chatting by not overriding their votes when sentences appear.

# How to use

Add a browser/HTML source in your streaming software and add the URL you need and configure as neccessary.

https://jamesbroadberry.github.io/TwitchPoll/?twitch={TwitchChannel}&interval={HowOftenTheUiUpdates}&show={NumberOfEntriesToShow}&fontSize={fontSizeInPixels}&fontColour={validHtmlColour}

Using the URL, modify the query parameters to your needs:

- **twitch** _(required)_
  - The Twitch Channel to monitor for responses
- **interval** _(not required, defaults to 250ms)_
  - How often the UI refreshes - data is always constantly processed when each message is recieved
- **show** _(not required, defaults to 5)_
  - How many items to show in the list of responses
- **fontSize** _(not required, defaults to 48)_
  - If you need a custom font size, leave as an integer in pixels
- **fontColour** _(not required, defaults to white)_
  - Change the font colour to something that better matches your stream

An example built URL would be:
https://jamesbroadberry.github.io/TwitchPoll/?twitch=thejrm_&fontColour=darkgrey

# Remarks

When there are no messages or if the socket fails to connect, the page will just stay blank for now
