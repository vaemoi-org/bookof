# Getting Started \(Dev Setup\)

> \(~~Pics~~ Commits\) or it didn't happen

To handle the different streams of changes that come along with a budding project idea, we employ various tools to get the most out of our workflow:

## Design

Designs should be iterative, Designs should be open and Designs should be examples. This translates to mean that we want our design, mocks, wireframes, etc. to be as easily accessible as our code. [Figma](https://figma.com) meets our requirements as a collaborative design tool. ** **

**We're currently looking for a lead designer to take over!!**

## Dev

#### Version Control

Writing code is easy, organizing code is hard. Version control \(VCS\) is the solution and git is the best implementation for us at the moment. The problem with git was our organization of branches and trying to track a release across different branches...

Then came _**git-flow**_!

Git flow came about from this [article](http://nvie.com/posts/a-successful-git-branching-model/) on a successful branching model with git from Vincent Driessen. Git flow is just a wrapper around git so even without using the CLI the same features are handy and available in git vanilla.

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

#### Personal Envs

Everyone has their own machine and that machine is special to them and tinkered to their liking.

![](/assets/toaster %281%29.png)

...and that's awesome, we shouldn't have to invade your digital space to get our code working. The solution is to use some package manager / environment manager that's powered by a config:

##### ruby

With ruby we found that these tools offer the best balance of usability and flexibility for all machines:

* _**ch-ruby**_** -** change ruby versions on demand
* _**ruby-install **_**- **install \(almost?\) any ruby version
* _**gem\_home**_** -** use a different folder as primary path for ruby gems
* _**bundler **_**- **"The best way to manage a Ruby application's gems"

Check [here](https://medium.com/@vaemoi/developing-revit-a-graphql-powered-ruby-cli-dcbcbee2b9e5) for an article/series on ruby development by us!

##### javascript

npm organization -&gt; [https://www.npmjs.com/org/vaemoi](https://www.npmjs.com/org/vaemoi)

For javascript we use yarn for package management and npm tasks to handle our tasks. Check [here](https://medium.com/@vaemoi/writing-wver-a-the-engine-for-rev-part-i-2984f2991dad) for an article/series on javascript development by us!

#### Continuous Integration/Delivery

Every change should be evaluated to see if an error has been introduced into the system. Along with test driven development, we use [GitLab CI/CD](https://docs.gitlab.com/ee/ci/) along with [Code Climate](/codeclimate.com) for static analysis.

