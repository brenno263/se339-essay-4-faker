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

The main issue with this turn of fate is that Faker had always been developed with a single install in mind, so it hardcoded all its localization and functions into one, rigid package.
PHP Faker continued with the same design principles as its predecessors, but that proved inconvenient for CI systems, where the package would have to be installed for every run of a test suite.
PHP Faker's creator lamented that he hadn't designed the package in a more modular way, to better enable efficient CI use. [(source)](https://marmelab.com/blog/2020/10/21/sunsetting-faker.html)

Now, a group of contributors has forked the [repository](https://github.com/FakerPHP/Faker) to try and continue its development for PHP.
However, we'll be turning our focus to a more mature, modernized Faker - Faker JS.

## Faker current

- Here we will talk about where Faker is currently, and how it differs from PHP in terms of design choices. Will also brielfy talk about tree shaking and what it is.

- This section focuses on more current developments in Faker JS (hereafter referred to as simply Faker).

After a kerfuffle with Faker JS' creator, the repository was recovered and a core team of contributors coalesced to back Faker.
The Faker JS team continued its development, noting the pitfalls of Faker PHP to avoid failing for the same reasons.

A big difference between the older PHP repository and this new JS one is its use of automation.
Let us start by looking at version 6 of Faker, which is demarked by the project being rewritten in typescript, adding documentation, setting up a CI/CD pipeline, and beginning to make major bug fixes regarding the implementation.
Faker JS now took advantage of Github Actions, along with a slew of testing suites, formatters, and linters to heavily automate new development.
Towards the end of version 6, various features such as random IMEI numbers and MongoDB ObjectId generation were also added.

Version 7 saw the Faker team overhauling the project again with continual code cleanup and improvements.
The ground was broken by removing code that had become deprecated, targeting es2020, and dropping support for Node v12, amongst other things.

As of version 7.5, most changes have centered around improving documentation, removing unused code, reducing code duplication, updating dependencies, and adding highly requested new features.

Currently, Faker sits at version 7.6 and has begun making major preparations for its version 8 release, in which its modules will be refactored to better support tree shaking.

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
