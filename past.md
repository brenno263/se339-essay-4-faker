## Faker PHP

There have been multiple versions of Faker in the past, but we're going to focus mainly on Faker PHP since its creator has a marvellous blog post about its design issues.
Originally, Faker was conceived by Jason Kohles as a Perl library to populate a database with fake, but believable data for rapid, safe development of database-heavy applications.
[(source)](https://metacpan.org/pod/Data::Faker).
A Ruby port was made soon after, with the exact same purpose.
[(source)](https://rubygems.org/gems/faker)

However, as the prevalence of software testing, and even test-driven development rose, Faker began to see a new purpose - generating test data for automatic tests.

The main issue with this turn of fate is that Faker had always been developed with a single install in mind, so it hardcoded all its localization and functions into one, rigid package.
PHP Faker continued with the same design principles as its predecessors, but that proved inconvenient for CI systems, where the package would have to be installed for every run of a test suite.
PHP Faker's creator lamented that he hadn't designed the package in a more modular way, to better enable efficient CI use. [(source)](https://marmelab.com/blog/2020/10/21/sunsetting-faker.html)
