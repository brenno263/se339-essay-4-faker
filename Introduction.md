### Introduction
Testing is an important aspect of coding, and generating data by hand is tedious.
Thus, Faker, which generates data for you, is a widely used package to generate realistic fake data.
Faker has been and is being developed in many different languages, including Perl (Original), Ruby, Python, PHP, and JavaScript.
Faker PHP was one of the most popular open-source packages, but it was eventually [archived](https://github.com/fzaninotto/Faker) due to its architectural flaws by the repository owner.
A group of contributors forked the [repository](https://github.com/FakerPHP/Faker) to try and continue its development.
Another popular open-source version is Faker JS.
After the original repository (the owner deleted) was recovered and a core team of contributors backed Faker, the Faker team continued its development, noting the pitfalls of Faker PHP to avoid failing for the same reasons.
A big difference between the PHP repository (the archive one) and the JS repository is the use of GitHub actions.
Faker JS takes advantage of them to increase the automatization of the review code review process.
Furthermore, Faker is taking action to restructure using Tree Shaking for their next big release. 
The Faker JS team is committed to modularizing their code to make it lightweight for users. 
The Faker JS team has released their [road map](https://fakerjs.dev/about/roadmap/v8.html), outlining their concerns and planned remedies.
