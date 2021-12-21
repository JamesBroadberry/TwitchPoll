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

Add a browser/HTML source in your streaming software and add the URL you need and configure as necessary.

https://jamesbroadberry.github.io/TwitchPoll/?twitch={TwitchChannel}&interval={HowOftenTheUiUpdates}&show={NumberOfEntriesToShow}&fontSize={fontSizeInPixels}&fontColour={validHtmlColour}&fontStrokeColour={fontStrokeColour}&fontStrokeWidth={fontStrokeWidth}

Using the URL, modify the query parameters to your needs:

- **twitch** _(required)_
  - The Twitch Channel to monitor for responses
- **interval** _(not required, defaults to 250)_
  - How often the UI refreshes **in milliseconds** - data is always constantly processed when each message is received
- **show** _(not required, defaults to 5)_
  - How many items to show in the list of responses
- **fontSize** _(not required, defaults to 48)_
  - If you need a custom font size, leave as an integer in pixels
- **fontColour** _(not required, defaults to black)_
  - Change the font colour to something that better matches your stream (if using a hex colour, you'll need to URL encode the '#' e.g. %23AAAAAA for #AAAAAA)
- **fontStrokeColour** _(not required, defaults to red)_
  - Change the font outline colour (if using a hex colour, you'll need to URL encode the '#' e.g. %23AAAAAA for #AAAAAA)
- **fontStrokeWidth** _(not required, defaults to 0px)_
  - Change the font outline width

An example built URL would be:
https://jamesbroadberry.github.io/TwitchPoll/?twitch=thejrm_&fontColour=white&fontStrokeColour=black&fontStrokeWidth=1
