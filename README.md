# yxes-config
Utility packages for the yxes namespace

These packages provide base functionality for objects in the `yxes` namespace.

## Installing

yxes-config can be installed with [pip](https://pip.pypa.io/):

```
$ git clone https://github.com/stephen-d-wells/yxes-config
$ cd yxes-config
$ pip setup.py install
```

## Usage

_Currently the only package available is the `find_dir` package._

### FindDir()

FindDir attempts to locate directories (folders) given the path of current
folder that it's run from. It does this by locating the real path that it's 
being run from and walking backwards looking for specific directories.

Currently, those directories are `conf`, `log` and `reports` but you are
encouraged to set your own.

#### Usage

basic

```
from yxes-config import FindDir

cd = FindDir()
print(cd.conf_dir)
print(cd.log_dir)
print(cd.report_dir)
```

advanced

```
from yxes-config import FindDir

cd = FindDir("my-reports")
print(cd.found_dir)
```

You may be wondering why anyone would ever need such a thing.

This started because I needed to have multiple configuration files from the same
codebase and I was too lazy to set up locations for each script. Instead I just
created a directory structure as follows:

```
projects/
  venv/
  proj1/
    bin/
    conf/
    log/
    reports/
  proj2/
    bin/
    conf/
    log/
    reports/
```

...and I could be sure it picked up the proper configuration files. If two
projects shared a directory, I could just link the directory or define it in
the base folder...

```
projects/
  conf/
  proj1/
    log/
    reports/
  proj2/
    log/
    reports/
```

# Contributing

Contributions are encouraged.

1. Fork the [repository](https://github.com/stephen-d-wells/yxes-config).
2. Create a [topic branch](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/).
3. Implement your feature or bug fix.
4. Add, commit, and push your changes.
5. Submit a [pull request](https://help.github.com/articles/using-pull-requests/).

# License

Copyright © 2020 Stephen D. Wells. It is free software, and may be redistributed
under the terms specified in the [LICENSE](LICENSE) file.

# Author

[Stephen D. Wells](https://linkedin.com/in/sdwells). All Rights Reserved.

