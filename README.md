HangFire <a href="https://ci.appveyor.com/project/odinserj/hangfire"><img title="Build status" width="113" src="https://ci.appveyor.com/api/projects/status/qejwc7kshs1q75m4?retina=true" /></a>
=========

#### [Official Site](http://hangfire.io) | [Blog](http://odinserj.net) | [Documentation](http://docs.hangfire.io) | [Forum](http://discuss.hangfire.io) | [Twitter](https://twitter.com/hangfire_net) | [NuGet Packages](https://www.nuget.org/packages?q=hangfire)

HangFire gives you a simple way to kick off **long-running processes** from the **ASP.NET request processing pipeline**. Asynchronous, transparent, reliable, efficient processing. No Windows service/ Task Scheduler required. Even ASP.NET is not required.

Improve the responsiveness of your web application. Do not force your users to wait when the application performs the following tasks:

- mass notifications/newsletter;
- batch import from xml, csv, json;
- creation of archives;
- firing off web hooks;
- deleting users;
- building different graphs;
- image processing;
- *…and so on.*

Just wrap your long-running process to a method and instruct HangFire to create a **background job** based on this method. All backround jobs are being saved to a **persistent storage** ([SQL Server](http://www.microsoft.com/sql‎) or [Redis](http://redis.io)) and performed on a dedicated **worker thread** in a reliable way inside or outside of your ASP.NET application.

HangFire is a .NET Framework alternative to [Resque](https://github.com/resque/resque), [Sidekiq](http://sidekiq.org), [delayed_job](https://github.com/collectiveidea/delayed_job).

Usage
------

**1. Install the package**

HangFire is available as a NuGet package. So, install it using the NuGet Package Console window:

```
PM> Install-Package HangFire
```

**2. Enqueue a background job**

You can run in background regular static or instance methods, just do the following:

```csharp
BackgroundJob.Enqueue(() => Console.WriteLine("Hello, world!"));
```

**3. Process it in background**

Processing is made inside a different worker thread. To start the worker pool, call:

```csharp
var server = new AspNetBackgroundJobServer();
server.Start();
```

This is incomplete list of features, to see all of them, check the [official site](http://hangfire.io) and the [documentation](http://docs.hangfire.io). For more instructions, see the [Quick start](http://docs.hangfire.io/en/latest/quickstart.html) guide.

Related Projects
-----------------

* [HangFire.Autofac](https://github.com/odinserj/HangFire.Autofac)
* [HangFire.Ninject](https://github.com/odinserj/HangFire.Ninject)
* [HangFire.SimpleInjector](https://github.com/devmondo/HangFire.SimpleInjector)

Roadmap
--------

* Full documentation for product and its API.
* More tutorials and articles that describe the features and use cases.
* Recurring jobs support to fully cover all background needs.
* Support for other job storages, including Microsoft Azure Storage.
* Make it easier to maintain jobs, even on large-scale systems.
* Deliver the solution to the 90% of ASP.NET developers :smile:.

Contributing
-------------

Open-source projects are developing more smoothly when all discussions are held in public. If you have **any** questions or suggestions, please open GitHub [issues](https://github.com/odinserj/HangFire/issues), mention [@hangfire_net](https://twitter.com/hangfire_net) on Twitter or simple ask a question on a documentation page.

Unfortunately, I can't do all the things at a time. And I appreciate any help related to the project:

* Code contributions, bug fixes.
* Spelling and grammar errors fixes.
* Web interface improvements.
* Documentation clarification.
* Code review.

To make a contribution, please fork a project, do the work and make a [pull-request](https://github.com/odinserj/HangFire/pulls).

License
--------

Copyright © 2013-2014 Sergey Odinokov.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with this program.  If not, see [http://www.gnu.org/licenses/](http://www.gnu.org/licenses).

[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/dd58c8cf730a3ed3675202135bb06025 "githalytics.com")](http://githalytics.com/odinserj/HangFire)
