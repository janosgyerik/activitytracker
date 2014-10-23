User actions
============

This document answers the question:

> What can you do with the app?

Overview
--------

The main features:

- Record activities + timestamp + gps, as if entered manually in a paper diary
- View recorded activities:
    - list of activities per time period: day / week / month / year / all
    - count of activities per time period: day / week / month / year / all
    - easy switch between time periods: next / prev buttons
    - option to select start date + end date / now

Nice to have features / things to add later:

- Synchronize between multiple devices
- Add tags on activities:
    - Group by tags in the various views
    - Option to select custom skin per tag (work / health / home / friends)
- View recorded activities on a map
- View nicely formatted report / send by email

The implementation will be centered around a RESTful API.
The idea is that anything can be implemented on top of a solid RESTful API:
mobile apps, web apps, command line clients.
(Btw, for fast prototyping in the beginning,
a command line client or web client might be the best.)

What is an activity?
--------------------

Something you want to track in your life.
For example:

- Beer night with friends
- Went to the gym to work out / zumba
- Went running
- Took the stairs
- Washed the dishes
- Cleaned the bathroom
- Cooked vs eat at restaurant
- Ate at McDonald's
- Studied vocabulary with Anki

Recording an activity
---------------------

Input fields:

- Short keyword: +autosuggest from recently used words to reduce typing
- Dropdown menu with recently used activity names
- Date and time: *now* by default, but editable using a nice calendar interface
- Later: add tags
- Later: add custom memo

Activities can have an optional long description which you can add or edit anytime.
When entering activities and when listing,
the short name should be used,
which might not be very descriptive, but something personal that you understand.

For example the above ideas with short names to use in the app:

- Beers -- Beer night with friends
- Gym -- Went to the gym to work out / zumba
- Running -- Went running
- Stairs -- Took the stairs
- Dishes -- Washed the dishes
- Bathroom -- Cleaned the bathroom
- Cooked -- Cooked vs eat at restaurant
- McDonald's -- Ate at McDonald's
- Anki -- Studied vocabulary with Anki

Other notes about the UI
------------------------

- It should be easy to record recurring activities
    - But not too easy to record something by mistake
- It should be possible to undo records
    - But not too easy to undo something by mistake

TODO
----

Some possible features I haven't decided about adding or leaving out?

- How to deal with positive and negative activities?
    - Should we distinguish?

- Would it make sense to add gamification in some way?
    - If yes, how, exactly?

- How about adding alerts if you've neglected some important activity for a long time?
    - For example, if an activity should be periodic, for example weekly,
      it can be nice if it becomes visible on the screen at the beginning
      of a new week so you don't forget to do it,
      and to make it easy to record it.

