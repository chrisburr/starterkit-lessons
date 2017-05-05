# Install party
{% objectives "Learning Objectives" %}
* Install git from source
* Install Anaconda
{% endobjectives %} 

In order to follow the Basics part of the workshop (first two days) you will
need to have recent versions of Python and Git installed either on your laptop
or on lxplus.
The instructions below explain how you can install Python and libraries for
scientific computing on lxplus by using the the Anaconda Python distribution.
After that, they explain how you can compile a recent version of git, because
the default version on lxplus is very old and doesn't support all the features
we'll need.

{% callout "Health warning" %}
Once you install things yourself you have an environment that is different
from the "standard" LHCb setup. It means you have to keep software up-to-date
yourself and when things start going wrong everyone will blame it on your
custom setup. Keep that in mind. With great tools comes great responsibility.
{% endcallout %} 

`Anaconda` is a complete set of `python` interpreter and useful libraries. For example
it comes with `ipython` pre-installed as well as `matplotlib` and `scikit-learn`.

To install `Anaconda` on lxplus or your Mac/Linux laptop follow these
instructions:

1. Visit the [`Anaconda downloads`](http://continuum.io/downloads) page.
2. Make sure to select the correct operating system (Windows, Mac or Linux)
3. For `lxplus` download the Linux 64bit - Python2.7 installer. To do this, right click on 64-bit installer for python 2.7 and click on copy link address.To begin installing this on `lxplus` you need to use wget:

   ```bash
   $ wget https://repo.continuum.io/archive/Anaconda2-4.2.0-Linux-x86_64.sh
   ```
   Where the argument to wget is the link address you copied. The link address may change as new versions of anaconda are released so be aware!
4. Then on `lxplus` type `bash Anaconda2-4.2.0-Linux-x86_64.sh` in the
   directory to which you downloaded the installer. Use `bash` no matter
   what your shell actually is.
5. Follow the on-screen instructions and go with the default answer to
   all questions.

This will install a modern set of python libraries to `~/anaconda`. This means you
need to have some free space on your AFS home directory. Once it is done check
that the installer added these two lines to your `.bashrc`:

```bash
# added by Anaconda2 4.2.0 installer
export PATH="~/anaconda2/bin:$PATH"
```

Log out of `lxplus` and back in. Now you should be able to start `python` as well as
`ipython`, etc.

{% callout "Removing Anaconda" %}
To remove `Anaconda` temporarily, simply comment out the two lines that were
added to your `.bashrc` file. To permanently remove it simply delete the `anaconda`
directory in your home directory.
{% endcallout %} 

To install `git` "from source" on `lxplus` follow these instructions.

1. Visit the [git repository](https://github.com/git/git) on github
2. Click on "releases", which takes you to the list of [all git releases](https://github.com/git/git/releases)
3. Download the `.tar.gz` for the latest release (v2.10.2) to `lxplus`:
```bash
$ wget https://github.com/git/git/archive/v2.10.2.tar.gz
```
4. unpack the `.tar.gz` with `tar xzf v2.10.2.tar.gz`
5. Change to the newly created `git-2.10.2` directory: `cd git-2.20.2`
6. Follow the [INSTALL](https://github.com/git/git/blob/master/INSTALL)
   instructions.
7. To install `git` in your home directory type:
```bash
$ export CURLDIR=$HOME/anaconda
$ mkdir $HOME/git-install-2.10.2
$ make prefix=$HOME/git-install-2.10.2
$ make prefix=$HOME/git-install-2.10.2 install
```
8. Add the following line to your `.bashrc`:
```bash
export PATH="$HOME/git-install-2.10.2/bin:$PATH"
```

{% callout "Removing git" %}
To temporarily remove `git` remove the line you added to your `.bashrc`, and delete
the `git-install-2.10.2` directory in your home directory to remove it permanently.
{% endcallout %} 
