# se339-essay-4-faker
Essay 4 for my Software Architecture class, where we examine some architecture choices in Faker JS


Faker's foreseeable future lies in Tree-Shaking, a process where dead code is removed. As of right now, there are three main versions that are in active development.
First and foremost is version 8.0, where a ton of tasks are underway. This incldues items such as renaming and moving modules, removing circular dependencies, standardizing 
function parameters, and more. The broad goal of the version 8 changes is to improve the modularity of the project, which is exemplified by the splitting of the Faker class into smaller units.
To use Faker to test, you must download the entirety of Faker. As a result, if you only use Faker for location testing, you are also forced to otherwise have
the other data types. Thus, version 8.1 seeks to rectify this and allow you to only download what you need. In addition to usability improvements this will reduce
the download size of the project.

While there are currently no further aspirations mentioned regarding Faker, it is clear to see that the developers wish to see Faker easier to use. Tree shaking represents their
acknowledgement  of the fact that while the project intensely useful, it also has clear ways in which it can further develop. 