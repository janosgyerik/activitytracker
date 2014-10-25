RESTful API
===========

The API (RESTful) is the centerpiece and driver of the implementation:
a rock solid RESTful API should make it easy to implement many kinds of client apps:

- mobile apps
- web apps
- command line clients, tools
- desktop apps

Authentication
--------------

Users should authenticate via OpenID, OAuth or similar.
We won't store user credentials and passwords.

All user data is private:
users can only access their own data, nobody else's.

Authentication tokens should not be part of the
RESTful API endpoint URLs, if possible.
Ideally these should be passed in the request headers somehow.
This seems to work today, see the GitHub API or Twitter API.

API methods
-----------

All API URLs below will be prefixed with `/api/:version/`,
for example `/api/v1`.

- `/activities` - get list of activity records
- `/activities/:id` - get detailed activity record
- `/tags` - get list of tag records
- `/tags/:id` - get detailed tag record
- `/entries` - get list of activity entries
  + `?from`
  + `?to`
  + `?period=day|week|month|year` - shortcut for corresponding `from`, `to`
- `/entries/:id` - get detailed activity entry

Activity
--------

- user: foreign key
- name
- description
- created
- updated

Tag
---

- user: foreign key
- slug
- name

ActivityTag
-----------

- user: foreign key
- activity: foreign key
- tag: foreign key

ActivityEntry
-------------

- user: foreign key
- activity: foreign key
- date
- memo
