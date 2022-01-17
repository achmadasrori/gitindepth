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

Example Result:
<br />
<img src="https://user-images.githubusercontent.com/18713143/149710372-36648673-10d5-4ea6-8db0-86dd43e1c031.png">

## Git Commits
Commits are information about any changes to any state stored by git from the initial state to the last state. Commit objects are stored in the form of a tree. commit data contains the following information:
1. Commit ID (SHA1)
2. author and commiter
3. date
4. message
5. parent commit (one or more)

the information in the commit data cannot be edited. but we can rollback to a previous commit.

<img src="https://user-images.githubusercontent.com/18713143/149713104-d087d84d-c8fd-4174-884c-c910d4d1c505.png">

## Gits Areas and Stashing
Git have 3 Areas. 
1. <b>Working Area</b> is where files that are not handled by git. These files are also referred to as "untracked files." 
2. <b>Staging Area</b> is files that are going to be a part of the next commit, which lets git know what changes in the file are going to occur for the next commit. The 
3. <b>repository</b> contains all of a project's commits.

