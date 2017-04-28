# Getting Started \(Dev Setup\)\(w.i.p\)

In the physical world we have a paper trail for two reasons: \(~~proof~~ logic\) and magic. The logic is simple and can be summarized as such:

> \(~~Pics~~ Commits\) or it didn't happen

In other words, if you can't talk about how your project grew from then did you really make it? Was this a though out process Or did you just throw it together at the last minute? Where did the inspiration come from, how were certain features implemented and why? These questions are easy to answer when the development process is tracked and logged.

To handle the different streams of changes that come along with a budding project idea, we employ various tools to turn our workflow data into valuable info:

## Design

Designs should be iterative, Designs should be open and Designs should be examples. This translates to mean that we want our design, mocks, wireframes, etc. to be as easily accessible as our code. [Figma](https://figma.com) meets our requirements as a collaborative design tool.

![](https://lh5.googleusercontent.com/13azgqaJX3KYaF8UhIPwDP0_GxxcAkIa1CxDfRf1eLQC-Yt2CxhQq4AZ3zNRS5YZSAjFhvKFmcuWTALFoDPUjlA7Q_9VOA62fmFU013MWdMGM69JzDi59aQFck0hqtyPoeu0mnqsbNw)

## DevOps

#### Hosting

\(Bitbucket \|\| Gitlab \) &gt; Github

read [this](https://github.com/dear-github/dear-github) first.

This is just our personal opinion at the moment but we find that [Bitbucket](https://bitbucket.org) provides some of the best tools and integrations for source code, not to mention they offer free private repos!

Alas the rest of the world doesn't share this opinion and insists on [Github](https://github.com/) only services...so we adapt but our main development stays in the bucket \(so to speak\).

#### Version Control

Writing code is easy, organizing code is hard. Version control \(VCS\) is the solution and git is the best implementation for us at the moment. The problem with git was our usage of branches and merging, we would often times use _**master**_ too often and branches would be alive too long that merges would require full team peer-programing sessions to complete...

Then came _**git-flow**_!

Git flow came about from this [article](http://nvie.com/posts/a-successful-git-branching-model/) on a successful branching model with git from Vincent Driessen.

![](https://lh6.googleusercontent.com/Z8uJe3BxTooZmCzPCcAh4rQMYsw7TMwFSDfKRxypWgY2XH069xNAnti7uVfMp1XwUipNIrG9jGRoEm_kXTyEBsrdIhMZHPiMm3GbMTZEi6x1KnTU_zXI139mj2l4rXwy6UEw6SrjAgY)

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

npm organization -&gt; [https://www.npmjs.com/org/vaemoi](https://www.npmjs.com/org/vaemoi)

For javascript we use yarn for package management and npm tasks to handle our tasks. While other options do exists and I've seem some awesome example used in production in my work experience, we find that those solution provide upfront benefits of easy setup but after awhile can become quite tangled but npm tasks provide basic tools that are scalable for small to medium size teams. Some of our favorite module are:

* _**concurrently **_**-** cross platform way to run tasks in parallel
* _**rimraf **_**-** cross platform way to remove files and folders recursively
* _**mkdirp**_ **-** cross platform way to create folders recursive

Check [here](https://medium.com/@vaemoi/writing-wver-a-the-engine-for-rev-part-i-2984f2991dad) for an article/series on javascript development by us!

#### Continuous Integration/Delivery

Every change should be evaluated to see if an error has been introduced into the system. Along with test driven development, we use [Bitbucket Pipelines](https://bitbucket.org/product/features/pipelines) inter-build testing

![](https://lh5.googleusercontent.com/5_WEPZ9j3Gzw_R3-_VfmwjiWVW5sV_MxhKRlAkjLpmdKXsEa7AZxJM98OFLu-7KNbQtER6oTpLzmzI4cakoDSTLdXyliOSffb01fRbjGK47MNFpPd-cIy8-16QrtCpjNRoe5KPcqRI8)

along with [Code Climate](/codeclimate.com) for static analysis.

![](https://lh3.googleusercontent.com/hTJtFPG5WES29oO3yFn26OLjKYVNdSiM958pkVpCTwPNPqEheXr-FTex4n3CyF2Fut8dyva3d503KwypQac6Q6BG6d2x4XKqSDgLJvQMGpIsQo0Ne-fYdfmVxPh6YzWpPn4ue9nxivI)

## Agile-ness

#### Task Management

Our initial try at task management / scrum / kanban began with [taiga.io](https://taiga.io)

but we eventually went with a more functional and dev centric approach with [bitbucket](https://bitbucket.org) and [bucketboard](https://marketplace.atlassian.com/plugins/bucketboard/cloud/overview?utm_source=BB-blog&utm_campaign=bitbucket_fy17q1-momentum-posts&_ga=1.104594437.463701457.1493158077).

![](https://lh5.googleusercontent.com/1cH1-Yg4Fw0ATNZGhRvmHb_QGztwXXptgmUg7TL2QDptx4mtXLyW3wvphlGPn-SY2Xh2EnuLHOqblSmx3oV-qCqTd_44HGLF-kXEl0v4XOPVvfD7ilYxTuABsSTjen3SvL0-dDc3vjg)

For daily standups we're creating a standup bot hosted on now.sh along with a status reporting cli tool and chrome extension that we're calling [_**gala**_](https://bitbucket.org/vaemoi/gala).

#### Time Management

For time management we recommend [WakaTime](https://wakatime.com) and their various plugins for editors and browsers. \(example from @brwnrclse\)

![](https://lh3.googleusercontent.com/_MbFVK-9BoHf6n8GSkVpI9UniYqF8D-YqADWeO6AO2A1f4M4014cNI7NgHVrxbV61DdPk1SGMPKo4USh8o6M8XM1A_caF1im0wP_5QqZRr2ryxl-Rn1diIhAgvWt_wrkzjCj4t6jJNI)

## Chat \(aka HQ\)

signin here -&gt; [https://vaemoi.slack.com](https://vaemoi.slack.com)

Request access from -&gt; [brwnrclse@gmail.com](mailto:brwnrclse@gmail.com)

Messages hold valuable information for both the now and the future so keeping them stored and indexed is always a plus! To accomplish this we use [slack](https://slack.com) \(duh\). Slack provides us with a centralized command center of sorts that we can program to send and receive messages to the various services we've employed.

* Hooks
  * Pipey - Bitbucket piplines status updates \(for each build\)
  * Loggy - Bitbucket push updates \(for each repo\)
* Bots
  * Status Cake - Website and Web server status updates \(pings\)
  * gala - A bot for status reporting and daily standups
* Apps
  * Figma - Providing team access to figma files



