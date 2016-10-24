Siftie
======

[Siftie](https://siftie.com) is a feed reader for teams. It's a web app, and
it's built with the [Meteor](https://www.meteor.com/) framework.

This repository is just the web app. There is a separate service that does the
actual crawling of feeds, and it's called [Feedie](https://github.com/nicksergeant/feedie).
You need to have both running if you want items to actually appear.

Demo
----

![https://siftie.com/img/demo.gif](https://siftie.com/img/demo.gif)

Install
-------

- `curl https://install.meteor.com/ | sh`

Develop
-------

1. `cd /path/to/siftie`
2. `meteor`
3. Visit [http://localhost:3000/](http://localhost:3000/).

Deploy
------

1. `git remote add dokku dokku@<your-dokku-server>:siftie`
2. `git push dokku`

You then need to configure the following environment variables:

```
ROOT_URL='http://siftie.com'
BUILDPACK_URL='https://github.com/AdmitHub/meteor-buildpack-horse.git'
MONGO_OPLOG_URL='mongodb://siftie_oplog:<db>@candidate.61.mongolayer.com:<port>,candidate.62.mongolayer.com:<port>/local?authSource=siftie'
MONGO_URL='mongodb://siftie_primary:<db>@candidate.61.mongolayer.com:<port>,candidate.62.mongolayer.com:<port>/siftie'
```
