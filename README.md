easydir
=======

Easy, pipe friendly parent directory navigation. A bit like [vim-easymotion](https://github.com/easymotion/vim-easymotion) for your current working directory.

Written in Python and works with both Python 2 and 3.

Inpsired by [zipline](https://github.com/adamnemecek/zipline) as [posted on Reddit](https://www.reddit.com/r/commandline/comments/50i6xf/zipline_the_cd_companion_utility_youve_always/).

Usage
-----

```sh
$ pwd
/home/vnguyen/projects/misc/easydir
$ easydir
/home/vnguyen/projects/misc/easydir
0    1       2        3    4
$ cd `easydir`
$ pwd
/home/vnguyen/projects/misc/easydir
$ easydir 1
/home
$ easydir 1 | xargs ls
vnguyen
$ cd `easydir 1`
$ pwd
/home
```

When no arguments are provided the numbered display is written to `stderr` but the current working directory is written to `stdout` (as a sane default). When a number argument is provided then appropriately trimmed path is written to `stdout`. This facilitates piping to other programs.

Installation
------------

The easiest way to install is probably with `pip`.

```sh
pip install easydir
```

An alternative way is via the `setup.py` script.

```sh
git clone https://github.com/vietjtnguyen/easydir.git
cd easydir
python setup.py install
```

Yet another way is to just copy the script into a folder available in your `PATH`.

```sh
git clone https://github.com/vietjtnguyen/easydir.git
cd easydir
cp easydir /usr/local/bin/
```

Note that you may require elevated privileges (`sudo`) if you are installing at the system level (i.e. not in a virtual environment).
