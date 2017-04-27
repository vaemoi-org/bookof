# Getting Started \(Our basic dev tools\)

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

Everyone has their own machine and that machine is special to them and tinkered to their liking.



![](/assets/toaster %281%29.png)

and that's awesome, we shouldn't have to invade your digital space to get our code working. The solution is to use some version manager for languages that can get hairy:

##### ruby

With ruby we found that the tools offered by offer the best balance of usability and flexibility for all machines:

* _**ch-ruby**_** -** change ruby versions on demand
* _**ruby-install **_**- **install \(almost?\) any ruby version
* _**gem\_home**_** -** use a different folder as primary path for ruby gems
* _**bundler **_**- **"The best way to manage a Ruby application's gems"

Check [here](https://medium.com/@vaemoi/developing-revit-a-graphql-powered-ruby-cli-dcbcbee2b9e5) for an article/series on ruby development by us!

##### python \(coming soon\)

Our python development hasn't started yet but we'll fill this in as we begin \(offer us suggestions on twitter @vaemoi or email us at dev@vaemoi.co\)

##### javascript \(needs editing\)

For javascript we use yarn for package management and npm tasks to handle our tasks. While other options do exists and I've seem some awesome example used in production in my work experience, we find that those solution provide upfront benefits of easy setup but after awhile can become quite tangled but npm tasks provide basic tools that are scalable for small to medium size teams. Some of our favorite module are:

* _**concurrently **_**-** cross platform way to run tasks in parallel
* _**rimraf **_**-** cross platform way to remove files and folders recursively
* _**mkdirp**_ **-** cross platform way to create folders recursive

Check [here](https://medium.com/@vaemoi/writing-wver-a-the-engine-for-rev-part-i-2984f2991dad) for an article/series on javascript development by us!

#### Continuous Integration

## Scrum

#### Task Management

#### Time Management

## Chat \(aka HQ\)

#### Messaging

#### Wiring Up



