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
### Areas
Git have 3 Areas. 
1. <b>Working Area</b> is where files that are not handled by git. These files are also referred to as "untracked files." 
2. <b>Staging Area</b> is files that are going to be a part of the next commit, which lets git know what changes in the file are going to occur for the next commit. The 
3. <b>Repository</b> contains all of a project's commits.

<br/>
<img src="https://user-images.githubusercontent.com/18713143/149714437-b5343c52-47d2-4f4a-8efd-b9379142107f.png">

### Stashing
Git can save uncommitted work to a git repo and is also safe from destructive operations. This is useful if you want to switch branches without committing first.
## References, Commits, Branches
Three types df git references:
1. <b>Tags & Annotated Tags</b> 
    - __Tag__ are just a simple pointer to a commit. When you create a tag with no arguments, it captures the value in HEAD
    - __Annotated Tags__ Point to a commit, but store additional information containing author, message, and date.
2. <b>Branches</b> 
    A branch is just a pointer to a particular commit. The pointer of the current branch changes as new commits are made.
3. <b>Head</b> 
    is how git knows what branch you’re currently on, and what the next parent will be. this is a place of information where we are currently actively working on a particular branch, tag, or commit

Separate what a tag is and what a branch is:
__Branch__
    The current branch pointer it moves with every new commit to the repository. use branches when your branch will change,  when new commits will added
__Tags__
    Tags are a pointer to a commit. it'a a snapshot. tags aren't meant to change. you tag version one of your release, then version two. you don't move a tag to another commit.
### Head-less / Detached Head
Git supports us to be able to checkout to a specific commit or tag instead of a branch.
### Dangling Commit
A commit that is unrelated to all existing references in our git project. git will put it as garbage collected. here we can find the reference and recover it.

## Merge and Rebasing
merge commit is just a marker of when a new feature was merged into master
### Fast Forwarding
Every once in while, you checkout in some branch you merge in your another branch and if there haven't been any additional changes to base branch by default git will merge with fast forwarded. 

Fast Forward happens when there are no commits on the base branch that occured after the feature branch was created. There's a clear path from the tip of the current branch to the tip of the branch.

jika anda tidak menginginkan metode default ini. seperti pada kasus anda ingin tetap merekam history merge, anda dapat melakukannya dengan menambah opsi `--no-ff` (No Fast Forward)

Use

```sh
git merge --no-ff
```

Before merge example : 

<img src="https://user-images.githubusercontent.com/18713143/149748753-66288ed5-a2fb-4ee4-8120-6204082124e1.png">

Merge fast forward example:

<img src="https://user-images.githubusercontent.com/18713143/149748770-39db5cd9-b402-48d0-b11a-b34bb6208d25.png">

Merge without fast forward example:

<img src="https://user-images.githubusercontent.com/18713143/149749898-c4308928-6668-4fc3-a839-01f08d9eba02.png">

### Git Rerere (Reuse Recorded Resolution)
Is tool for conflicted merges. this tool is a really, really helpful tool. In a workflow employing relatively long lived topic branches, the developer sometimes needs to resolve the same conflicts over and over again until the topic branches are done (either merged to the "release" branch, or sent out and accepted upstream).

This command assists the developer in this process by recording conflicted automerge results and corresponding hand resolve results on the initial manual merge, and applying previously recorded hand resolutions to their corresponding automerge results.

reference : [https://git-scm.com/docs/git-rerere].