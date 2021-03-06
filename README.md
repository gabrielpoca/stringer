# Stringer

[![Build Status](https://api.travis-ci.org/swanson/stringer.svg?style=flat)](https://travis-ci.org/swanson/stringer)
[![Code Climate](https://codeclimate.com/github/swanson/stringer.svg?style=flat)](https://codeclimate.com/github/swanson/stringer)
[![Dependency Status](https://gemnasium.com/swanson/stringer.svg)](https://gemnasium.com/swanson/stringer)

### A self-hosted, anti-social RSS reader.

Stringer has no external dependencies, no social recommendations/sharing, and no
fancy machine learning algorithms.

But it does have keyboard shortcuts and was made with love!

![](screenshots/instructions.png) ![](screenshots/stories.png)
![](screenshots/feed.png)

## Installation

Stringer is a Ruby (2.3.0+) app based on Sinatra, ActiveRecord, PostgreSQL,
Backbone.js and DelayedJob.

Instructions are provided for deploying to [Docker](docs/docker.md).

## Niceties

### Keyboard Shortcuts

You can access the keyboard shortcuts when using the app by hitting `?`.

![](screenshots/keyboard_shortcuts.png)

### Fever API

Stringer implements a clone of [Fever's API](http://www.feedafever.com/api) so
it can be used with any mobile client that supports Fever.

![image](https://f.cloud.github.com/assets/56947/546236/68456536-c288-11e2-834b-9043dc75a087.png)

Use the following settings:

```
Server: {path-to-stringer}/fever (e.g. http://reader.example.com/fever)

Email: stringer (case-sensitive)
Password: {your-stringer-password}
```

If you have previously setup Stringer, you will need to migrate your database
and run `rake change_password` for the API key to be setup properly.

### Translations

Stringer has been translated to [several other languages](config/locales). Your
language can be set with the `LOCALE` environment variable.

If you would like to translate Stringer to your preferred language, please use
[LocaleApp](http://www.localeapp.com/projects/4637).

### Clean up old read stories

You can clean up old stories by running: `rake cleanup_old_stories`

By default, this removes read stories that are more than 30 days old (that are
not starred). You can either run this manually or add it as a scheduled task.

## Development

Run the Ruby tests with `rspec`.

Run the Javascript tests with `rake test_js` and then open a browser to
`http://localhost:4567/test`.

### Getting Started

Run the following commands.

```sh
bundle install
rake db:migrate
bin/server
```

The application will be running on port `3000`.

You can launch an interactive console (a la `rails c`) using `bin/console`.

## Acknowledgements

Most of the heavy-lifting is done by
[`feedjira`](https://github.com/feedjira/feedjira) and
[`feedbag`](https://github.com/dwillis/feedbag).

General sexiness courtesy of
[`Twitter Bootstrap`](http://twitter.github.io/bootstrap/) and
[`Flat UI`](http://designmodo.github.io/Flat-UI/).

ReenieBeanie Font Copyright &copy; 2010 Typeco (james@typeco.com). Licensed
under [SIL Open Font License, 1.1](http://scripts.sil.org/OFL).

Lato Font Copyright &copy; 2010-2011 by tyPoland Lukasz Dziedzic
(team@latofonts.com). Licensed under
[SIL Open Font License, 1.1](http://scripts.sil.org/OFL).

## Contact

If you have a question, feature idea, or are running into problems, our
preferred method of contact is to open an issue on GitHub. This allows multiple
people to weigh in and we can keep everything in one place. Thanks!

## Maintainers

Matt Swanson, [mdswanson.com](http://mdswanson.com),
[@\_swanson](http://twitter.com/_swanson)

Victor Koronen, [victor.koronen.se](http://victor.koronen.se/),
[@victorkoronen](https://twitter.com/victorkoronen)
