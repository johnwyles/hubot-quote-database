# Hubot Quote Database
A Hubot quote database script which adds/removes/purges-all quotes to a quote database and recalls them by regular expression, subtext, or ID

# Installation
Put this line under dependencies in your package.json:
    "hubot-quote-database": "",

Next open the external-scripts.json file and add:
    "hubot-quote-database"

Now run NPM install and restart your hubot.

# Examples
    hubot addquote Look at me! I'm on TV
    hubot addquote johnwyles: I really enjoy the band TV on the radio
    hubot quote *TV*
      => Look at me! I'm on TV! [ID: 23]
      => johnwyles: I really enjoy the band TV on the radio [ID: 24]
    hubot rmquote 23
      => Do you really want to purge the quote [ID: 23] from the database?  Type 'rmquote 23 seriously' if you are sure!
    hubot rmquote 23 seriously
      => The quote has been removed from the database [ID: 23].
    hubot quote *TV*
      => johnwyles: I really enjoy the band TV on the radio [ID: 24]
    hubot quote
      => Hello World!  This is a random quote from the database! [ID: 832]
    hubot quote 832
      => Hello World!  This is a random quote from the database! [ID: 832]
    hubot quote (F|f)oobar
      => Foobar [ID: 56]
      => foobar [ID: 57]
      => Foobar is barfoo [ID: 58]
      => There were [2] more quotes found.  To retrieve all of these run again with quoteall.  For example: 'quoteall (F|f)oobar'.
    hubot quoteall (F|f)oobar
      => Foobar [ID: 56]
      => foobar [ID: 57]
      => Foobar is barfoo [ID: 58]
      => I once ate a foobar [ID: 61]
      => Foobar FTW! [ID: 62]
    hubot purgeallquotes
      => Do you really want to purge all of the quotes in the database?  Type 'purgeallquotes seriously' if you are sure!
    hubot purgeallquotes seriously
      => All quotes have been purged from the databasee.
