# Installing DSSG pre-requisites on OS X

This guide will help you install all pre-requisites to be ready for the summer.

## Step 1. Install Homebrew

[Homebrew](http://brew.sh/) is a package manager for OS X that will make your life a lot easier.

To install, open Terminal.app and execute the following:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Now you can do:

```bash
brew install wget
```

<details>
<summary>If that doesn't work...</summary>

If that doesn't work, check that you have `/usr/local/bin` and `/usr/local/sbin` in your `PATH`
by typing:

```bash
echo $PATH
```

The results should look something like:

```bash
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
```

If `/usr/local/bin` is not in there, you can add it to your `~/.profile` by typing

```bash
echo 'export PATH=/usr/local/bin:$PATH' >> ~/.profile
```

If still not working. [Ask for help](https://github.com/dssg/hitchhikers-guide/blob/master/curriculum/0_before_you_start/prerequisites/README.md#asking-for-help).

</details>

## Step 2. Install tools

### Minimum pre-requisites

1. SSH - this comes already installed with OS X
2. Git - this comes already installed with OS X
3. Python 3.7 - `brew install python`

### Code editors and IDEs

We recommend the following code editors or IDEs:

* Visual Studio Code - `brew cask install visual-studio-code`
* Sublime Text - `brew cask install sublime-text`
* Atom - `brew cask install atom`
* PyCharm - `brew cask install pycharm-ce`

**Note:** applications installed via `brew cask install` will be available in `~/Applications`

## Step 3. Install Python tools

For managing your python environments and packages, we recommend to use [Pipenv][pipenv].

To install it:

    pip install pipenv

Then navigate to a project folder and install some data science packages by using

    pipenv install jupyter ipython numpy scipy pandas scikit-learn seaborn [...]

Now you can run

    pipenv shell

to switch to that environment, and run

    jupyter notebook

to start coding!

<details>
<summary>Why Pipenv?</summary>

Pipenv is a tool that aims to bring the best of all packaging worlds (bundler, composer, npm, cargo, yarn, etc.) to the Python world.

It automatically creates and manages a virtualenv for your projects, as well as adds/removes packages from your Pipfile as you install/uninstall packages. It also generates the ever-important `Pipfile.lock`, which is used to produce deterministic builds.

The problems that Pipenv seeks to solve are multi-faceted:

* You no longer need to use `pip` and `virtualenv` separately. They work together.
* Managing a `requirements.txt` file can be problematic, so Pipenv uses `Pipfile` and `Pipfile.lock` to separate abstract dependency declarations from the last tested combination.
* Hashes are used everywhere, always. Security. Automatically expose security vulnerabilities.
* Strongly encourage the use of the latest versions of dependencies to minimize security risks arising from outdated components.
* Give you insight into your dependency graph (e.g. `$ pipenv graph`).
* Streamline development workflow by loading `.env` files.

</details>

### What about conda?

If you prefer `conda` you're free to use it! However, `conda` sometimes has outdated packages or doesn't have some packages at all, unlike `pip` which is the official Python package manager, which means you'll have to deal with both package managers at the same time, leading to various issues.

The main distribution, Anaconda, occupies a large amount of space with a lot of packages you may not need. We recommend you to download [miniconda](https://docs.conda.io/en/latest/miniconda.html) instead.


[pipenv]: https://pipenv.pypa.io/en/latest/