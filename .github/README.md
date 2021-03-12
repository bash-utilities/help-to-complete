# Help To Complete
[heading__top]:
  #help-to-complete
  "&#x2B06; Builds tab-completion configurations from `--help` output"


Builds tab-completion configurations from `--help` output


## [![Byte size of Help To Complete][badge__main__help_to_complete__source_code]][help_to_complete__main__source_code] [![Open Issues][badge__issues__help_to_complete]][issues__help_to_complete] [![Open Pull Requests][badge__pull_requests__help_to_complete]][pull_requests__help_to_complete] [![Latest commits][badge__commits__help_to_complete__main]][commits__help_to_complete__main]


---


- [:arrow_up: Top of Document][heading__top]

- [:building_construction: Requirements][heading__requirements]

- [:zap: Quick Start][heading__quick_start]

  - [:floppy_disk: Clone][heading__clone]
  - [:heavy_plus_sign: Install][heading__install]
  - [:fire: Uninstall][heading__uninstall]
  - [:arrow_up: Upgrade][heading__upgrade]
  - [:bookmark_tabs: Documentation][heading__documentation]

- [&#x1F9F0; Usage][heading__usage]

- [:symbols: API][heading__api]

- [&#x1F5D2; Notes][heading__notes]

- [:chart_with_upwards_trend: Contributing][heading__contributing]

  - [:trident: Forking][heading__forking]
  - [:currency_exchange: Sponsor][heading__sponsor]

- [:card_index: Attribution][heading__attribution]

- [:balance_scale: Licensing][heading__license]


---



## Requirements
[heading__requirements]:
  #requirements
  "&#x1F3D7; Prerequisites and/or dependencies that this project needs to function properly"


This repository makes use of Git Submodules to track dependencies, to avoid incomplete downloads clone with the `--recurse-submodules` option...


```Bash
git clone --recurse-submodules git@github.com:bash-utilities/help-to-complete.git
```


To update tracked Git Submodules issue the following commands...


```Bash
git pull

git submodule update --init --merge --recursive
```


To force upgrade of Git Submodules...


```Bash
git submodule update --init --merge --recursive --remote
```


> Note, forcing and update of Git Submodule tracked dependencies may cause instabilities and/or merge conflicts; if however everything operates as expected after an update please consider submitting a Pull Request.


______


## Quick Start
[heading__quick_start]:
  #quick-start
  "&#9889; Perhaps as easy as one, 2.0,..."


> Perhaps as easy as one, 2.0,...


---


### Clone
[heading__clone]:
  #clone
  "&#x1f4be;"


Clone this project...


```Bash
mkdir -vp ~/git/hub/bash-utilities

cd ~/git/hub/bash-utilities

git clone --recurse-submodules git@github.com:bash-utilities/help-to-complete.git
```


---


### Install
[heading__install]:
  #install
  "&#x2795;"


Install via `make install` command...


```Bash
cd ~/git/hub/bash-utilities/help-to-complete

make install
```


---


### Uninstall
[heading__uninstall]:
  #uninstall
  "&#x1f525;"


Uninstall via `uninstall` Make target...


```Bash
cd ~/git/hub/bash-utilities/help-to-complete

make uninstall
```


... Which will remove symbolic links for script(s) and manual page(s).


---


### Upgrade
[heading__upgrade]:
  #upgrade
  "&#x2b06;"


To update in the future use `make upgrade` command...


```Bash
cd ~/git/hub/bash-utilities/help-to-complete

make upgrade
```


---


### Documentation
[heading__documentation]:
  #documentation
  "&#x1F4D1;"


After installation, documentation may be accessed via `man` command, eg...


```Bash
man help-to-complete
```


______


## Usage
[heading__usage]:
  #usage
  "&#x1F9F0; How to utilize this repository"



Generally the only required parameter to define is `--executable`, eg...


```Bash
sudo help-to-complete --executable script-name
```


However, it is possible to define where completion configurations are saved, as well as the option that prints help/usage information for an executable...


```Bash
sudo help-to-complete --executable script-name\
                      --completion-dir /usr/share/bash-completion/completions\
                      --help-option '--help'
```


For example to save bash completion configurations to current repository may be similar to...


```Bash
mkdir -vp "${PWD}/bash-completion"

help-to-complete --executable script-name\
                 --completion-dir "${PWD}/bash-completion"
```


______


## API
[heading__api]:
  #api
  "&#x1F523; Parameter documentation"


- `-c` or `--clobber` - Overwrites preexisting completion configuration

- `-h` or `--help` - Prints this message and exits

- `-l` or `--license` - Prints copyright for this script and exits

- `-v` or `--verbose` - Prints messages about actions

- `-V` or `--version` - Prints version for this script and exits

- `--completion-dir` _`<directory>`_ - Directory to that completion configuration will be saved to

- `--executable` _`<executable>`_ - **Required** name of executable to parse help documentation from

- `--help-option` _`<parameter>`_ - Option executable uses to print help/usage

- `--parameter-pattern` _`<regexp>`_ - Regular expression for parsing parameters from help/usage output


______


## Notes
[heading__notes]:
  #notes
  "&#x1F5D2; Additional things to keep in mind when utilizing this project"


Help/usage of target executable should be formatted similar to output of `help-to-complete` script, which is _mostly_ compatible with `help2man` parsing requirements, eg...


```
<description>


Usage: <name> [OPTIONS]...


Options:
-h    --help
    Prints this message and exits

-l    --license
    Prints copyright for this script and exits

-v    --verbose
    Prints messages about actions

-V    --version
    Prints version for this script and exits

-d    --directory "some/where"
    Directory path used by <name>

-e    --executable "ls"
    Executable called within <name>

-w    --words "spam|flavored|ham"
    Key word modifiers

-p    --pattern "^(-{1,2}[a-zA-Z]){1,}"
    Regular expression


Examples:
    <name> -v --words spam
```


Output of `help-to-complete` should be considered a _starting-point_, and depending upon executable further customization may be required.


This repository may not be feature complete and/or fully functional, Pull Requests that add features or fix bugs are certainly welcomed.


______


## Contributing
[heading__contributing]:
  #contributing
  "&#x1F4C8; Options for contributing to help-to-complete and bash-utilities"


Options for contributing to help-to-complete and bash-utilities


---


### Forking
[heading__forking]:
  #forking
  "&#x1F531; Tips for forking help-to-complete"


Start making a [Fork][help_to_complete__fork_it] of this repository to an account that you have write permissions for.


- Add remote for fork URL. The URL syntax is _`git@github.com:<NAME>/<REPO>.git`_...


```Bash
cd ~/git/hub/bash-utilities/help-to-complete

git remote add fork git@github.com:<NAME>/help-to-complete.git
```


- Commit your changes and push to your fork, eg. to fix an issue...


```Bash
cd ~/git/hub/bash-utilities/help-to-complete


git commit -F- <<'EOF'
:bug: Fixes #42 Issue


**Edits**


- `<SCRIPT-NAME>` script, fixes some bug reported in issue
EOF


git push fork main
```


> Note, the `-u` option may be used to set `fork` as the default remote, eg. _`git push -u fork main`_ however, this will also default the `fork` remote for pulling from too! Meaning that pulling updates from `origin` must be done explicitly, eg. _`git pull origin main`_


- Then on GitHub submit a Pull Request through the Web-UI, the URL syntax is _`https://github.com/<NAME>/<REPO>/pull/new/<BRANCH>`_


> Note; to decrease the chances of your Pull Request needing modifications before being accepted, please check the [dot-github](https://github.com/bash-utilities/.github) repository for detailed contributing guidelines.


---


### Sponsor
  [heading__sponsor]:
  #sponsor
  "&#x1F4B1; Methods for financially supporting bash-utilities that maintains help-to-complete"


Thanks for even considering it!


Via Liberapay you may <sub>[![sponsor__shields_io__liberapay]][sponsor__link__liberapay]</sub> on a repeating basis.


Regardless of if you're able to financially support projects such as array-splice that bash-utilities maintains, please consider sharing projects that are useful with others, because one of the goals of maintaining Open Source repositories is to provide value to the community.


______


## Attribution
[heading__attribution]:
  #attribution
  "&#x1F4C7; Resources that where helpful in building this project so far."


- [GitHub -- `github-utilities/make-readme`](https://github.com/github-utilities/make-readme)

- [StackOverflow -- Read lines from a file into a Bash array](https://stackoverflow.com/questions/11393817/)


______


## License
[heading__license]:
  #license
  "&#x2696; Legal side of Open Source"


```
Builds tab-completion configurations from `--help` output
Copyright (C) 2021 S0AndS0

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, version 3 of the License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```


For further details review full length version of [AGPL-3.0][branch__current__license] License.



[branch__current__license]:
  /LICENSE
  "&#x2696; Full length version of AGPL-3.0 License"


[badge__commits__help_to_complete__main]:
  https://img.shields.io/github/last-commit/bash-utilities/help-to-complete/main.svg

[commits__help_to_complete__main]:
  https://github.com/bash-utilities/help-to-complete/commits/main
  "&#x1F4DD; History of changes on this branch"


[help_to_complete__community]:
  https://github.com/bash-utilities/help-to-complete/community
  "&#x1F331; Dedicated to functioning code"


[issues__help_to_complete]:
  https://github.com/bash-utilities/help-to-complete/issues
  "&#x2622; Search for and _bump_ existing issues or open new issues for project maintainer to address."

[help_to_complete__fork_it]:
  https://github.com/bash-utilities/help-to-complete/
  "&#x1F531; Fork it!"

[pull_requests__help_to_complete]:
  https://github.com/bash-utilities/help-to-complete/pulls
  "&#x1F3D7; Pull Request friendly, though please check the Community guidelines"

[help_to_complete__main__source_code]:
  https://github.com/bash-utilities/help-to-complete/
  "&#x2328; Project source!"

[badge__issues__help_to_complete]:
  https://img.shields.io/github/issues/bash-utilities/help-to-complete.svg

[badge__pull_requests__help_to_complete]:
  https://img.shields.io/github/issues-pr/bash-utilities/help-to-complete.svg

[badge__main__help_to_complete__source_code]:
  https://img.shields.io/github/repo-size/bash-utilities/help-to-complete


[sponsor__shields_io__liberapay]:
  https://img.shields.io/static/v1?logo=liberapay&label=Sponsor&message=bash-utilities

[sponsor__link__liberapay]:
  https://liberapay.com/bash-utilities
  "&#x1F4B1; Sponsor developments and projects that bash-utilities maintains via Liberapay"

