# Gloomy Companion

This is a web-app for managing the monster ability decks in the board game [Gloomhaven](https://boardgamegeek.com/boardgame/174430/gloomhaven)

This is a variant of the original app (https://github.com/johreh/gloomycompanion) that I've made for my personal use. You may use it too.

I have stripped out a lot of the fancy stuff that differentiates this app from just using the monster ability decks. My version does not include HP of monsters nor stats/traits of monsters and it leaves the card text as e.g. "Attack +0" rather than calculating the final "Attack 3" for you. I'm sure many people prefer the fancy version, but I don't, hence these changes.

I've also made some attempts to make the card layout match the physical game's more closely.

You can run it from the web directly on <https://scmccarthy.github.io/gloomycompanion/>.

You can also download it and run it locally without internet connection. Click __Clone or download__ above, then __Download ZIP__. Unpack the ZIP and start the app by opening `index.html`.

If you want to add new cards, you need to update `cards.js`. The decks has the following syntax:
```
{ name: "Name of monster"
, cards:
  [ [false, "42", "* First line", "** sub-line 1", "** sub-line 2", "* Second line"]
  , [true,  "55", "* Card text"]
  ]
}
```
The value in the first column is `true` if the deck shall be reshuffled after that card, `false` otherwise. The second colum is card initiative value. The following values is the card text, one row per column.

A single `*` means a top-level action. Double asterisk `**` means it modifies the previous action. Commonly used text snippets can be expanded using macros. E.g. `%move%` expands to the text _Move_ followed by the move icon, `%immobilize%` expands to _IMMOBILIZE_ followed by the immobilization icon. The list of available macros can be seen in `macros.js`.
