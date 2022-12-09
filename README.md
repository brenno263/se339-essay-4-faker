# Outline

This document serves to outline the basic structure of the document. It is subject to change.

Suggestions appreciated.

## Introduction

Testing is an important aspect of coding, and sometimes there isn't a readily available dataset.
Generating data by hand can tedious, so Faker generates that data for you.
Faker is a widely popular library which is implemented in many different languages, including Perl, Ruby, Python, PHP, and JavaScript.
Faker PHP was one of the most popular open-source packages, but it was eventually [archived](https://github.com/fzaninotto/Faker) due to its architectural flaws by the repository owner.
Another popular open-source version is Faker JS.
The Faker JS team has worked to create a much more modern, modular, and automated code base than any other before it, and they have big plans going forwards.
The Faker JS team has released their [road map](https://fakerjs.dev/about/roadmap/v8.html), outlining their concerns and planned remedies.

## Faker in the past & motivations, + Death of Faker PHP

- This section will discuss the rise of software testing, how faker was originally concieved to assist with testing, and some of the design decisions in previous versions of faker.

- Here we also will highlight the rise of CI/CD and containerization, and how in this new environment, PHP faker crumbled.

There have been multiple versions of Faker in the past, but we're going to focus mainly on Faker PHP since its creator has a marvellous blog post about its design issues.
Originally, Faker was conceived by Jason Kohles as a Perl library to populate a database with fake, but believable data for rapid, safe development of database-heavy applications.
[(source)](https://metacpan.org/pod/Data::Faker).
A Ruby port was made soon after, with the exact same purpose.
[(source)](https://rubygems.org/gems/faker)

However, as the prevalence of software testing, and even test-driven development rose, Faker began to see a new purpose - generating test data for automatic tests.

The main issue with this turn of fate is that Faker had always been developed with a single install in mind, so they followed the same design principles as their predecessors.
Namely, all the localization was hardcoded into one rigid package.

Most users use only a single locale, so they need only a tiny fraction of the library.
But because it was all tied into one package, they would have to download all 3MB every time.
As CI systems became popular, this became somewhat of an issue.
The package would have to be installed for every commit, every run of a test suite.
PHP Faker's creator lamented that he hadn't designed the package in a more modular way, to better enable efficient CI use. [(source)](https://marmelab.com/blog/2020/10/21/sunsetting-faker.html)

The package was far larger than it needed to be.
In fact, he did some math, estimating that over Faker PHP's lifespan its 3MB package had been downloaded over 121 million times.
At this rate, he calculated that Faker PHP had itself emitted over 11 metric tons of CO2.

![Daily Installs Graph](https://marmelab.com/static/0f0ac106722a0cdec40564596865cdbb/df77d/packagist_stats.webp "Daily Installs Graph")

Now, a group of contributors has forked the [repository](https://github.com/FakerPHP/Faker) to try and continue its development for PHP.
However, we'll be turning our focus to a more mature, modernized Faker - Faker JS.

## Faker current

- Here we will talk about where Faker is currently, and how it differs from PHP in terms of design choices. Will also brielfy talk about tree shaking and what it is.

- This section focuses on more current developments in Faker JS (hereafter referred to as simply Faker).

After a kerfuffle with Faker JS' creator, the repository was recovered and a core team of contributors coalesced to back Faker.
The Faker JS team continued its development, noting the pitfalls of Faker PHP to avoid failing for the same reasons.

The present version of Faker differs from the past in several key areas. First, the folder structure has changed and now includes a source and documentation folder, in addition to several integrations that allow Faker to be automated.

More recent versions of Faker, starting at version 6, demarked by being rewritten in typescript, have new features such as better documentation, setting up a CI/CD pipeline, and making an increased effort to fix major bugs within the project.
Faker JS now took advantage of Github Actions, along with a slew of testing suites, formatters, and linters to heavily automate new development.
Towards the end of version 6, new features such as random IMEI numbers and MongoDB ObjectId generation were added.

Version 7 saw the Faker team overhauling the project again with continual code cleanup and improvements. The ground was broken by removing code that had become deprecated, targeting es2020, and dropping support for Node v12, amongst other things.

As of version 7.5, most changes have centered around improving documentation, removing unused code, reducing code duplication, updating dependencies, and adding highly requested new features.

Currently, Faker sits at version 7.6 and has begun making major preparations for its version 8 release, in which its modules will be refactored and reorganized.

## Lessons taken in Faker JS + Version 8

- Now, we'll talk about what the folks at Faker JS learned from the past, how they surmounted some issues, and how they plan to take this further with version 8.

Going forward the Faker development team is putting an emphasis on refactoring.
Part of this process is tree-shaking, a process where dead code is removed.
In addition to this, the organization of the project is being overhauled.
This includes fixing circular dependencies, shuffling and renaming modules, as well as standardizing function parameters.

The final goal of this effort is to make Faker easier to use while removing un-necessary complexity.
The most important step is to break down the Faker class into smaller units.
This will have four levels: CoreFaker, BaseFaker, LocalizedFaker, and Faker as we know it now.
With CoreFaker being the base level, each will add more complexity, as CoreFaker will only hold a seed and rng logic.

Further development in Faker is helping to fix technical debt it has obtained, no matter how small.
This includes renaming and shuffling modules into a new structure, as well as fixing fundamental seed randomization not working as intended.

## Conclusion

One can only wonder if the Faker Maintainers were recently visited by the Ghost of Faker Past, Ghost of Faker Present, and Ghost of Faker Future.
With the recently developed plans for Faker's future, it seems the Maintainers have taken a good long look at the current state of Faker and the previous state of Faker to aid in the trajectory of Faker's future.

Ghost of Faker Past, would of have shown the Maintainers an early, large, and rigid version of today's Faker.

Whereas the Ghost of Faker Present would have boasted about the major overhauls, many automations, and the transition from PHP to JS.

Completing this eerie dream with the Ghost of Faker Future, the Maintainers would have been shown a future where Faker had grown into one large complex object, thus enticing the Maintainers to alter their current trajectory.
A new trajectory in which Faker becomes smarter, cleaner, and easier to use.
Faker knows where it has been, Faker knows where it is, and Faker knows where it wants to go.
