# Development Workflows

When it came to development, no matter how close we were physically because every team member has his or her own day job and life outside of the project, we decided to operate like a distributed team. This meant _**everything from messaging to designing to testing and releasing had to be accessible by any team member from any machine.**_ From this single requirement came our collection of tools mentioned in [Setup ](/chapter1.md)and the following workflow suggestions.

### Editors

No matter what editor you use it should have some form of a project management system in place:

* Sublime Text uses the `.sublime-project`file to handle projects with the following format learn more [here](https://www.sublimetext.com/docs/3/projects.html):

![](/assets/Screen Shot 2017-04-28 at 2.15.27 AM.png)

* ...Add other editors here

SublimeText packages and starter config can be found [here](https://bitbucket.org/brwnrclse/dotty)

### Ruby

#### Linting

For linting in ruby we use [rubocop](http://rubocop.readthedocs.io/en/latest/) and a default config to use can be found [here](https://bitbucket.org/brwnrclse/dotty)

#### Gems

###### Setting up dependencies

Start by install [bundler](/bundler.io)

Then install dependencies by running bundler from the project folder:

```
bundle
```

###### Testing

From within the project directory tweak the `Rakefile` run:

```bash
bundle rake
```

You can also install you current version of the gem locally and play around with it using

```bash
bundle rake build
bundle rake install # or install:local if you don't have a network connection
```

Also also you can just run the gem's code live in a shell using IRB via the script \(usually in\) `bin/console` like so \(from within the gem folder\):

```
./bin/console
```

###### Release

To release the module you need to have an account with RubyGems and be added to the `email` portion of the `.gemspec`

file.

Releasing is as easy as:

```bash
bundle rake build
bundle rake release
```

### Javascript

###### Setting up dependencies

Start by installing [npm](https://docs.npmjs.com/getting-started/installing-node)

Then install [yarn](https://yarnpkg.com/en/)

If you're wondering why you need both, check [here](https://code.facebook.com/posts/1840075619545360) and ask questions [here](https://twitter.com/yarnpkg)

When installing packges make sure to ALWAYS USE YARN, this ensures that the correct versions are installed on each machine.

###### Managing Things \(building, concatting, testing , converting images, etc\)

We simply define a task in the section of the `package.json` :

![](/assets/Screen Shot 2017-04-28 at 2.51.40 AM.png)

Then we can run the task like so:

![](/assets/Screen Shot 2017-04-28 at 2.52.01 AM.png)

### Static Sites and Assets

For static sites we like using [pug](https://pugjs.org/) \(fomerly jade\) and [stylus](http://stylus-lang.com). We picked these tools because they simply make writing HTML and CSS easier and still allow plain HTML and CSS to be used if that's your fancy.

Pug also supports the normal things that most templating langauges support like, partials and extension so you can do things like make a basic layout file:

![](/assets/Screen Shot 2017-04-28 at 3.01.47 AM.png)

And extend it to use in each page:

![](/assets/Screen Shot 2017-04-28 at 3.03.42 AM.png)

Stylus works in much the same way for CSS providing variables for css via the `$` symbol

![](/assets/Screen Shot 2017-04-28 at 3.06.14 AM.png)

and copy parent selectors using the `&` operator:

![](/assets/Screen Shot 2017-04-28 at 3.06.29 AM.png)

