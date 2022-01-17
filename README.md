# gitindepth
## What is git?
Git is a distributed version control system for collaborating and managing the code from our projects to make it easier and minimize errors when the code from our projects is handled by multiple editors.

## Git Data Storage
Git stores information comparing it to a key-value store where data is the value and the hash (40-digit hexadecimal number) of the data is the key.

## Git Blobs an Tree
git stores project information and its metadata into blobs, trees, and commit objects, with each object storing different parts of the project such as its contents and folder structure into a .git folder. Deleting the .git directory, the information and history of the project are gone, but not the files of the project.

Command for view the tree of .git directory
```sh
tree .git
```

Example Result
<img width="500" alt="Screen Shot 2022-01-17 at 11 57 37" src="https://user-images.githubusercontent.com/18713143/149710372-36648673-10d5-4ea6-8db0-86dd43e1c031.png">