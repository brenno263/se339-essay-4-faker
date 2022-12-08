Faker's foreseeable future lies in Tree-Shaking, a process where dead code is removed. 
For Faker specifically, this comes in the form of version 8.0. 
Various changes and improvements such as removing circular dependencies, renaming and moving modules, as well as standardizing function parameters are taking place. 

The final goal of this effort is to make Faker easier to use while removing un-necessary complexity.
The most important step is to break down the Faker class into smaller units. 
This will have four levels: CoreFaker, BaseFaker, LocalizedFaker, and Faker as we know it now.
With CoreFaker being the base level, each will add more complexity, as CoreFaker will only hold a seed and rng logic. 

Further development in Faker is helping to fix technical debt it has obtained, no matter how small. 
This includes renaming and shuffling modules into a new structure, as well as fixing fundamental seed randomization not working as intended.

