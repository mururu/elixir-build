**This repository is archived**

---

# elixir-build

elixir-build is an [exenv](https://github.com/mururu/exenv) plugin
that provides an `exenv install` command to compile and install
different versions of Elixir on UNIX-like systems.

You can also use elixir-build without exenv in environments where you
need precise control over Elixir version installation.

elixir-build is the Elixir version of ruby-build. Thanks to @sstephenson!

### Prerequisite

Erlang, version R16B or later.

## Installation

### Installing as an exenv plugin (recommended)

Installing elixir-build as an exenv plugin will give you access to the
`exenv install` command.

    git clone git://github.com/mururu/elixir-build.git ~/.exenv/plugins/elixir-build

This will install the latest development version of elixir-build into
the `~/.exenv/plugins/elixir-build` directory. From that directory, you
can check out a specific release tag. To update elixir-build, run `git
pull` to download the latest changes.

### Installing as a standalone program (advanced)

Installing elixir-build as a standalone program will give you access to
the `elixir-build` command for precise control over Elixir version
installation. If you have exenv installed, you will also be able to
use the `exenv install` command.

    git clone git://github.com/mururu/elixir-build.git
    cd elixir-build
    ./install.sh

This will install elixir-build into `/usr/local`. If you do not have
write permission to `/usr/local`, you will need to run `sudo
./install.sh` instead. You can install to a different prefix by
setting the `PREFIX` environment variable.

To update elixir-build after it has been installed, run `git pull` in
your cloned copy of the repository, then re-run the install script.

## Usage

### Using `exenv install` with exenv

To install a Elixir version for use with exenv, run `exenv install` with
the exact name of the version you want to install. For example,

    exenv install 0.7.0

Elixir versions will be installed into a directory of the same name
under `~/.exenv/versions`.

To see a list of all available Elixir versions, run `exenv install --list`.
You may also tab-complete available Elixir
versions if your exenv installation is properly configured.

### Using `elixir-build` standalone

If you have installed elixir-build as a standalone program, you can use
the `elixir-build` command to compile and install Elixir versions into
specific locations.

Run the `elixir-build` command with the exact name of the version you
want to install and the full path where you want to install it. For
example,

    elixir-build 0.6.0 ~/local/0.6.0

To see a list of all available Elixir versions, run `elixir-build
--definitions`.

Pass the `-v` or `--verbose` flag to `elixir-build` as the first
argument to see what's happening under the hood.

### Keeping the build directory after installation

Both `elixir-build` and `exenv install` accept the `-k` or `--keep`
flag, which tells elixir-build to keep the downloaded source after
installation.

Source code will be kept in a parallel directory tree
`~/.exenv/sources` when using `--keep` with the `exenv install`
command.

### Installing Elixir of specified revision (Advanced)

You can install Elixir of specified revision by specifying the sha1.
For example,

```
exenv install --add g7d22146
exenv install g7d22146
```

## Version History

#### 20130921

 * Add --add option (@khia)

#### 20130609

 * Add install_git_sha1

#### 20121120

 * fork [ruby-build](https://github.com/sstephenson/ruby-build)

### License

(The MIT License)

Copyright (c) 2011 Sam Stephenson, Yuki Ito

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
