> [!CAUTION]
> **This repository is archived and no longer actively maintained.**
>
> We are no longer accepting issues, feature requests, or pull requests.
> For additional support or questions, please visit the [Express.js Discussions page](https://github.com/expressjs/express/discussions).


A comparison of server-side node frameworks.
This may include frameworks with a browser-side component.

### Frameworks

Only frameworks with over 1,000 stars are currently added.
Feel free to add your own.
The frameworks are listed by number of watchers, descending, as of March 18, 2014.

| Framework              | Sponsor(s) / Author(s)                                | Watchers | Stars  |
------------------------:|-------------------------------------------------------|----------|--------|
| [Meteor][meteor]       | [Meteor Development Group][meteorgroup]               | 973      | 11,687 |
| [Express][express]     | [StrongLoop][strongloop] / [TJ Holowaychuk][tj]       | 828      | 12,824 |
| [Sails][sails]         | [Mike McNeil][mikemcneil]                             | 485      | 5,582  |
| [Koa][koa]             | [TJ Holowaychuk][tj]                                  | 232      | 3,160  |
| [Derby][derby]         | [Nate Smith][natesmith] [Brian Noguchi][briannoguchi] | 213      | 3,079  |
| [Kraken][kraken]       | [PayPal][paypal]                                      | 210      | 2,424  |
| [Hapi][hapi]           | [Walmart Labs][walmart]                               | 204      | 1,981  |
| [Connect][connect]     | [Sencha Labs][senchalabs]                             | 202      | 4,180  |
| [LoopBack][loopback]   | [StrongLoop][strongloop]                              | 187      | 2,602  |
| [Restify][restify]     | [Mark Cavage][markcavage]                             | 122      | 2,001  |
| [Geddy][geddy]         | [Matthew Eernisse][mattheweernisse]                   | 101      | 1,703  |
| [CompoundJS][compound] | [Anatoliy Chakkaev][1602]                             | 91       | 1,542  |
| [Flatiron][flatiron]   | [Nodejitsu][nodejitsu]                                | 75       | 1,146  |

### Stack Integration

Traditionally, frameworks are explicitly server-side. However, there are now frameworks that are vertically integrated, i.e. integrate the client with the server.

| Framework  | Server-side | Client-side |
|-----------:|-------------|-------------|
| Meteor     | ✓           | ✓           |
| Express    | ✓           |             |
| Sails      | ✓           |             |
| Koa        | ✓           |             |
| Derby      | ✓           | ✓           |
| Kraken     | ✓           |             |
| Hapi       | ✓           |             |
| Connect    | ✓           |             |
| LoopBack   | ✓           | ✓           |
| Restify    | ✓           |             |
| Geddy      | ✓           | ✓           |
| CompoundJS | ✓           |             |
| Flatiron   | ✓           |             |

### Dependencies

Some frameworks are built upon other frameworks.

| Framework  | Dependencies                     |
|-----------:|----------------------------------|
| Meteor     |                                  |
| Express    | [Connect][connect] for `< 4.0.0` |
| Sails      | [Express][express]               |
| Koa        |                                  |
| Derby      |                                  |
| Kraken     | [Express][express]               |
| Hapi       |                                  |
| Connect    |                                  |
| LoopBack   | [Express][express]               |
| Restify    |                                  |
| Geddy      |                                  |
| CompoundJS |                                  |
| Flatiron   |                                  |

### Source Lines of Code

This is the lines of code a framework uses, not including comments.
This is used to gauge complexity and modularity of a framework.

| Framework  | Source Lines of Code | Version      |
|-----------:|----------------------|--------------|
| Meteor     |                      |              |
| Express    | 1,150                | 4.0.0-rc3    |
| Sails      | 5,350                | 0.10.0-rc4   |
| Koa        | 550                  | 0.5.1        |
| Derby      | 1,450                | 0.6.0-alpha3 |
| Kraken     | 680                  | 0.7.         |
| Hapi       | 4,750                | 3.0.0        |
| Connect    | 120                  | 3.0.0-rc1    |
| LoopBack   | 10,472               | 2.8.0        |
| Restify    | 3,970                | 2.6.3        |
| Geddy      | 5,660                | 0.12.4       |
| CompoundJS | 3,010                | 1.1.13-1     |
| Flatiron   | 581                  | 0.3.11       |

Note: [sloc](https://www.npmjs.org/package/sloc) is used to calculate the SLOC. Most are simply counted by running `sloc lib` and `lines of source code` is used.

### Middleware/Plugin Signature

Different frameworks use plugins and middleware differently.
Some use objects, others use functions.
Some work with node's `req` and `res` objects, whereas many others do not.

A framework "supports node" if node's `req` and `res` objects are passed to plugins and middleware,
and using node's `req` and `res` objects is supported.

| Framework  | Signature                                          | Supports Node |
|-----------:|----------------------------------------------------|---------------|
| Meteor     |                                                    | ×             |
| Express    | `app.use(function (req, res, next) {})`            | ✓             |
| Sails      | `function(req, res, next)`                         | ✓             |
| Koa        | `app.use(function* (next) {})`                     | ×             |
| Derby      |                                                    |               |
| Kraken     | `app.use(function (req, res, next) {})`            | ✓             |
| Hapi       | `app.ext('onRequest', function (req, next) {})`    | ×             |
| Connect    | `app.use(function (req, res, next) {})`            | ✓             |
| LoopBack   | `app.use(function (req, res, next) {})`            | ✓             |
| Restify    | `app.use(function (req, res, next) {})`            | ✓             |
| Geddy      | `this.before(function (req, res) {})`              | ✓             |
| CompoundJS |                                                    |               |
| Flatiron   |                                                    |               |

### Error Handling

Error handling in node.js is wonderful!
The current solution to catch uncaught exceptions (emitters and streams throwing errors everywhere) is to use [domains][domains] (unless you listen to every error).
If a framework does not handle uncaught exceptions, then domains should probably use [domains][domains].

| Framework  | Middleware/Plugin                                                | Uncaught Exceptions Handling    |
|-----------:|------------------------------------------------------------------|---------------------------------|
| Meteor     |                                                                  |                                 |
| Express    | `next(err)` / `app.use(function (err, req, res, next) {})`       | ×                               |
| Sails      |                                                                  |                                 |
| Koa        | try/catch                                                        | × - Unnecessary with generators |
| Derby      |                                                                  |                                 |
| Kraken     | `next(err)` / `app.use(function (err, req, res, next) {})`       |                                 |
| Hapi       |                                                                  | [domains][domains]              |
| Connect    | `next(err)` / `app.use(function (err, req, res, next) {})`       | ×                               |
| LoopBack   | `next(err)` / `app.use(function (err, req, res, next) {})`       | x                               |
| Restify    | `next(err)`                                                      |                                 |
| Geddy      |                                                                  |                                 |
| CompoundJS |                                                                  |                                 |
| Flatiron   |                                                                  |                                 |

### Control Flow

Most frameworks use only node's traditional callbacks for control.
As we move towards ES6, we will see frameworks that use generators and promises to avoid callback hell.
Any framework without a `control flow` is assumed to use callbacks unless otherwise specified.

| Framework  | Control Flow          |
|-----------:|-----------------------|
| Meteor     | [fibers][fibers]      |
| Express    |                       |
| Sails      |                       |
| Koa        | generators - [co][co] |
| Derby      |                       |
| Kraken     |                       |
| Hapi       |                       |
| Connect    |                       |
| LoopBack   |                       |
| Restify    |                       |
| Geddy      |                       |
| CompoundJS |                       |
| Flatiron   |                       |

### Included Features

If a feature is not included, there is a very good possibility that it can be used via middleware or plugin.
Which features a framework includes or does not include is unimportant - its philosophy is.

| Framework  | Content Negotiation | Cookie Management | Routing | View System | Body Parsing | Multipart Parsing |
|-----------:|---------------------|-------------------|---------|-------------|--------------|-------------------|
| Meteor     |                     |                   |         |             |              |                   |
| Express    | ✓                   | ✓                 | ✓       | ✓           |              |                   |
| Sails      | ✓                   | ✓                 | ✓       | ✓           | ✓            | ✓                 |
| Koa        | ✓                   | ✓                 |         |             |              |                   |
| Derby      |                     |                   |         |             |              |                   |
| Kraken     | ✓                   | ✓                 | ✓       | ✓           |              |                   |
| Hapi       |                     |                   |         |             |              |                   |
| Connect    |                     |                   |         |             |              |                   |
| LoopBack   | ✓                   | ✓                 | ✓       | ✓           |              |                   |
| Restify    | ✓                   |                   | ✓       |             | ✓            | ✓                 |
| Geddy      | ✓                   | ✓                 | ✓       | ✓           | ✓            |                   |
| CompoundJS |                     |                   |         |             |              |                   |
| Flatiron   |                     |                   |         |             |              |                   |

| Framework  | Session Management  | CSRF Protection | Compression | File Uploads | Basic Authentication |
|-----------:|---------------------|-----------------|-------------|--------------|----------------------|
| Meteor     |                     |                 | ✓           |              | ✓                    |
| Express    |                     |                 |             | ✓            |                      |
| Sails      | ✓                   | ✓               |             | ✓            |                      |
| Koa        |                     |                 |             |              |                      |
| Derby      |                     |                 |             |              |                      |
| Kraken     |                     |                 |             |              |                      |
| Hapi       |                     |                 |             |              |                      |
| Connect    |                     |                 |             |              |                      |
| LoopBack   |                     |                 |             | ✓            |                      |
| Restify    |                     |                 | ✓           |              | ✓                    |
| Geddy      | ✓                   | ✓               |             |              | ✓                    |
| CompoundJS |                     |                 |             |              |                      |
| Flatiron   |                     |                 |             |              |                      |

- Content Negotiation - ability to negotiation server response types and the request's acceptable types.
- Cookie Management - ability to parse cookies as well as set cookies
- Routing -
- View System - ability to choose a templating system and render templates by their name
- Body Parsing - ability to parse urlencoded and json request bodies
- Multipart Parsing - ability to part multipart request bodies
- Session Management - ability to provide non-authenticated cookie-based sessions
- CSRF Protection - built in CSRF protection
- Compression - built-in gzip and deflate response compression
- File Uploads - built-in ability to send local files to the client
- Basic Authentication

### Database

| Framework  | Required Databases     | Recommended Databases | Compatible Databases                                   |
|-----------:|------------------------|-----------------------|--------------------------------------------------------|
| Meteor     | [MongoDB][mongodb]     |                       |                                                        |
| Express    |                        |                       |                                                        |
| Sails      |                        |                       | MongoDB, MySQL, Postgres                               |
| Koa        |                        |                       |                                                        |
| Derby      |                        |                       |                                                        |
| Kraken     |                        |                       |                                                        |
| Hapi       |                        |                       |                                                        |
| Connect    |                        |                       |                                                        |
| LoopBack   |                        |                       | Microsoft SQL Server, MongoDB, MySQL, Oracle, Postgres |
| Restify    |                        |                       |                                                        |
| Geddy      |                        |                       | LevelDB, MongoDB, MySQL, Postgres, Riak, SQLite        |
| CompoundJS |                        |                       |                                                        |
| Flatiron   |                        |                       |                                                        |

### Templating

| Framework  | Required Templating Systems | Recommended Templating Systems | Compatible Templating Systems         |
|-----------:|-----------------------------|--------------------------------|---------------------------------------|
| Meteor     | [handlebars][handlebars]    |                                |                                       |
| Express    |                             |                                | [consolidate][consolidate]            |
| Sails      |                             |                                | [consolidate][consolidate]            |
| Koa        |                             |                                |                                       |
| Derby      |                             | [handlebars][handlebars]-like  |                                       |
| Kraken     |                             | [dustjs][dustjs]               | [consolidate][consolidate]            |
| Hapi       |                             |                                |                                       |
| Connect    |                             |                                |                                       |
| LoopBack   |                             |                                | [consolidate][consolidate]            |
| Restify    |                             |                                |                                       |
| Geddy      |                             |                                | handlebars, EJS, Jade, Swig, mustache |
| CompoundJS |                             |                                |                                       |
| Flatiron   |                             |                                |                                       |

[consolidate][consolidate] means that the framework supports any templating system supported by consolidate.js.

## Contributing

When adding a new framework, you __must__ add the simplest metadata such as links, SLOC, stack, and dependencies.
Frameworks without a decent amount of stars are not welcomed.
Do not spam your brand new framework.

Performance comparisons are __not__ welcomed.

Metadata should be updated for the __latest stable versions__, including release candidates, but not including alpha or beta versions.

## License

The MIT License (MIT)

Copyright (c) 2014 Jonathan Ong me@jongleberry.com

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

[strongloop]: http://strongloop.com/
[loopback]: http://loopback.io/
[express]: http://expressjs.com/
[koa]: https://github.com/koajs/koa
[connect]: https://github.com/senchalabs/connect
[meteor]: https://github.com/meteor/meteor
[tj]: http://github.com/tj
[derby]: https://github.com/codeparty/derby
[sails]: https://github.com/balderdashy/sails
[compound]: https://github.com/1602/compound
[geddy]: https://github.com/geddy/geddy
[flatiron]: https://github.com/flatiron/flatiron
[hapi]: https://github.com/spumko/hapi
[walmart]: http://www.walmartlabs.com
[meteorgroup]: https://www.meteor.com
[mikemcneil]: https://github.com/balderdashy
[natesmith]: https://github.com/nateps
[briannoguchi]: https://github.com/bnoguchi
[1602]: https://github.com/1602
[nodejitsu]: http://nodejitsu.com
[mattheweernisse]: https://github.com/mde
[senchalabs]: http://senchalabs.org
[co]: https://github.com/visionmedia/co
[kraken]: http://krakenjs.com
[paypal]: http://paypal.github.io
[handlebars]: http://handlebarsjs.com
[mongodb]: http://www.mongodb.org
[dustjs]: https://github.com/akdubya/dustjs
[restify]: https://github.com/mcavage/node-restify
[markcavage]: https://github.com/mcavage
[fibers]: https://github.com/laverdet/node-Fibers
[consolidate]: https://github.com/visionmedia/consolidate.js/
[domains]: http://nodejs.org/api/domain.html
