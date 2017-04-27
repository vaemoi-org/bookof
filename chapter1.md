# Tracking Changes

In the physical world we have a paper trail for two reasons: \(~~proof~~ logic\) and magic. The logic is simple and can be summarized as such:

> \(~~Pics~~ Commits\) or it didn't happen

In other words, if you can't talk about how your project grew from then did you really make it? Was this a though out process Or did you just throw it together at the last minute? Where did the inspiration come from, how were certain features implemented and why? These questions are easy to answer when the development process is tracked and logged.

To handle the different streams of changes that come along with a budding project idea, we employ various tools to turn our workflow data into valuable info:

## Design

## DevOps

#### Version Control

Writing code is easy, organizing code is hard. Version control \(VCS\) is the solution and git is the best implementation for us at the moment. The problem with git was our usage of branches and merging, we would often times use _**master**_ too often and branches would be alive too long that merges would require full team peer-programing sessions to complete...

Then came _**git-flow**_!

Git flow came about from this [article](http://nvie.com/posts/a-successful-git-branching-model/) on a successful branching model with git from Vincent Driessen.

The cheatsheet [here](http://danielkummer.github.io/git-flow-cheatsheet/index.fr_FR.html) provides a great workflow example but we'll show it here quickly.



```bash
# Begin a new git flow
git flow init

# Start a new feature
git flow feature start new_feature

# Make a new feature available to team members
git flow feature publish new_feature

## or 
git push -u origin feature/new_feature

# Grab a new feature from a team member
git flow feature pull new_new_feature

## or
git pull origin  feature/new_new_feature

# Start a new release
git flow release start v1.0.0

# ..do some release stuff (bump version numbers, run builds, document, lint, etc)

# Finish a release
git flow release finish v1.0.0 
```

The cool thing about git flow is that once a release is finished the master branch is updated but not pushed, leaving you the freedom to do any other tasks needed before releasing to a platform or server.

#### Personal Envs

#### Continuous Integration

## Scrum

#### Task Management

#### Time Management

## Chat \(aka HQ\)

#### Messaging

#### Wiring Up



