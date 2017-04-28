# Development Workflows \(w.i.p\)

When it came to development, no matter how close we were physically because every team member has his or her own day job and life outside of the project, we decided to operate like a distributed team. This meant _**everything from standups and designing to testing and releasing had to be accessible by any team member from any machine.**_ From this single requirement came our collection of tools mentioned in [Chapter 1 ](/chapter1.md)and the following workflow suggestions.

### Editors

No matter what editor you use it should have some form of a project management system in place:

* Sublime Text uses the `.sublime-project`file to handle projects with the following format learn more [here](https://www.sublimetext.com/docs/3/projects.html):

![](/assets/Screen Shot 2017-04-28 at 2.15.27 AM.png)

* ...Add other editors here

SublimeText packages and starter config can be found [here](https://bitbucket.org/brwnrclse/dotty)

### Ruby

#### Linting

For linting in ruby we use [rubocop](http://rubocop.readthedocs.io/en/latest/) and a default config to use can be found [here](https://bitbucket.org/brwnrclse/dotty)

#### Gem

When creating a ruby gem the first thing to do is setup the environment by setting the ruby version with a `.ruby-version` file:

![](/assets/Screen Shot 2017-04-28 at 2.28.20 AM.png)

Next you install bundler and tell it to install dependencies to a local folder and set that folder as the GEM\_HOME:

![](/assets/Screen Shot 2017-04-28 at 2.30.49 AM.png)

![](/assets/Screen Shot 2017-04-28 at 2.36.44 AM.png)

![](/assets/Screen Shot 2017-04-28 at 2.31.26 AM.png)

#### Rails

Coming soon!

### Javascript \(with npm\)

Start by installing [npm](https://docs.npmjs.com/getting-started/installing-node)

Then install [yarn](https://yarnpkg.com/en/)

If you're wondering why you need both, check [here](https://code.facebook.com/posts/1840075619545360) and ask questions [here](https://twitter.com/yarnpkg)

When installing packges make sure to ALWAYS USE YARN, this ensures that the same packages and version are installed on each machine.

Since we use npm scripts to power our devops tasks, we have the entire npm directory of tools to use!

We simply define a task in the section:

![](/assets/Screen Shot 2017-04-28 at 2.51.40 AM.png)

Then we can run the task like so:

![](/assets/Screen Shot 2017-04-28 at 2.52.01 AM.png)

### Python \(with pypi\)

Coming soon!

### Static Site

For static sites we like using [pug](https://pugjs.org/) \(fomerly jade\) and [stylus](http://stylus-lang.com). We picked these tools because they simply make writing HTML and CSS easier and still allow plain HTML and CSS to be used if that's your fancy.

Pug also supports the normal things that most templating langauges support like, partials and extension so you can do things like make a basic layout file:

![](/assets/Screen Shot 2017-04-28 at 3.01.47 AM.png)

And extend it to use in each page:

![](/assets/Screen Shot 2017-04-28 at 3.03.42 AM.png)

Stylus works in much the same way but it also provides variables for css via the `$` symbol

![](/assets/Screen Shot 2017-04-28 at 3.06.14 AM.png)

and copy parent selectors using the `&` operator:

![](/assets/Screen Shot 2017-04-28 at 3.06.29 AM.png)

