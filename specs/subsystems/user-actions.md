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

Personal goals: this app can help you to ... :

- lose weight
- eat healthier
- drink less alcohol
- ...

In settings, you can enter *personal goals*,
which add more indicators to help you track your progress.

Nice to have features / things to add later:

- Synchronize between devices
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

Synchronization
---------------

To keep it simple, the first release will need internet,
to talk to the central server of the RESTful API,
and eliminate the need of synchronization.

Future releases can introduce the notion of local caching
and implement synchronization between clients and server.

Positive and negative activities
--------------------------------

Some activities are positive in nature:

- Went to the gym
- Washed the dishes
- ...

Others are negative:

- Had beers
- Watched TV series
- ...

One way to distinguish these activities is by using tags.

Another way will be using the *impact* value with personal goals.

TODO: see https://habitrpg.com for more inspiration, maybe.

Alerts and recurring activities
-------------------------------

It might be interesting to set periodic alerting for some activities.
For example, you should go to the gym at least once a week.
The alert doesn't have to be a real alarm (but it can be).
It can simply pop up in the view as a *suggestion*.
Being in the view would also give an easy way to record the activity (no need to type, etc).

The opposite also makes sense for negative activities:
you should not go to the pub more than once a week.

TODO: should we add features for this, and how exactly should it work?

TODO
----

Some possible features I haven't decided about adding or leaving out?

- Would it make sense to add gamification in some way?
    - If yes, how, exactly?
    - See https://habitrpg.com for inspiration maybe. Any others?

