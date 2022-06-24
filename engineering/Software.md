<img align="right" src="https://github.com/braingu/tadpole/blob/master/images/TLP/TLPAmber.png">

## Tools: Software

Software choices should be entirely up to the developer; there will be different requirements based on role. These guidelines are offered as a starting place only; corrections and discussion happily welcomed.


### General Awareness

You want to stay current on new software, vulnerability announcements, patches, company sales, and everything else that might impact the viability of any given software resource. Subscribe to announcements for any product you’re supporting.


#### Sources

You can engage in either a “pull” or a “push” approach, depending on whether you want generalized information delivered to you, or you’re going to look for information on a specific technical challenge. So whether you opt for passive information collection (by allowing the algorithm to retrieve articles for you, or setting up alerts) or active information collection by performing searches, these resources can be valuable for you.


##### Google

You can rely on the Google algorithm to provide suggestions and newsworthies, if you use Google to search for terms in the course of your work (and you have your browser set to show you for it.)


##### BrainGu Slack Channels


  #nerd-devops


  #nerd-insecurity


##### Vulnerabilities

* [https://cve.mitre.org/](https://cve.mitre.org/)

* [https://otx.alienvault.com/](https://otx.alienvault.com/)


##### General


[https://www.reddit.com/r/devsecops/](https://www.reddit.com/r/devsecops/)



### IDE/Editor

You can use any editor which has syntax highlighting, is plugable, multi-pane, and has good find/replace with regex support, for example, [atom](https://atom.io/), [VS Code](https://code.visualstudio.com/), and [Sublime](https://www.sublimetext.com/).


#### Plugins

*   Language support
    *   [https://atom.io/packages/ide-json](https://atom.io/packages/ide-json)
    *   [https://atom.io/packages/language-groovy](https://atom.io/packages/language-groovy)
*   Various linters
*   Beautifiers
    *   [https://atom.io/packages/atom-beautify](https://atom.io/packages/atom-beautify)
*   Spell Check
    *   [https://atom.io/packages/spell-check](https://atom.io/packages/spell-check)


### Linux Shell

*   Linux subsystem for Windows has made this better on a Windows host
*   Completion packages (bash-completion, zsh-completion, etc)
*   Usually uses out-of-the-box .gitignore, etc. You may or may not have the opportunity/need to customize an environment. Sam’s gotten in the habit of not customizing, because it’s the shortest path.


### Package Manager

*   [Homebrew](https://brew.sh/) for OS X
*   [Linuxbrew](https://docs.brew.sh/Homebrew-on-Linux) + WSL
*   OS native for Linux distributions
*   Language specific (python-pip, npm, gem, maven, etc)


### Password Manager

There should be some sort of BrainGu standard guidance. We’re creating an exec summary, and will get a definitive answer on this. Work in progress [here](https://docs.google.com/document/d/112f9hWDpEV_Wneq_DhnjSzev9p3FuMoYAWtroBxxTV4/edit?usp=sharing).

### SCIF

If you're in a SCIF/closed network, use [devdocs.io](https://devdocs.io/)
### Tools

#### [Ansible](https://www.ansible.com/)

*   Ansible-galaxy
*   Ansibl-lint
*   molecule

#### [Cloud CLI](https://www.ibm.com/cloud/cli)

*   awscli
*   gcloud cli
*   azure cli


#### Git

It’s important to understand the principles of Git, and not just rely on the IDE’s Git client, because the IDE masks what you don’t know. IDE Git clients take liberties and do strange things that result in lost code. It’s better to understand what is going on and issue the commands yourself.

#### [OpenSSL](https://www.openssl.org/)

(see: Troubleshooting)

#### [Packer](https://www.packer.io/)

#### SSH client

Preferably, don’t use PuTTY...because it’s not the best tool for the job. It may be the only tool, in which case whatever, but with the advent of Windows subsystem, it’s just not the best (more cumbersome and difficult, not efficient).

#### Terminal (MacOS)
*    [iterm2](https://iterm2.com/)
*    [zsh](https://www.zsh.org/)
*    [oh-my-zsh](https://ohmyz.sh/)


#### [Terraform](https://www.terraform.io/)




#### [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

#### Linters

*   [Yamllint](https://pypi.org/project/yamllint/)
*   [Jsonlint](https://jsonlint.com/?code=)
*   [Flake8](https://pypi.org/project/flake8/)


#### [Markdown Architectural Decision Records](https://adr.github.io/madr/)



### Runtimes

Ideally you’ll want to use the most current version, although there's always things like virtual environments for python and node, and a range of Java versions. The big thing here is to avoid running versions with known vulnerabilities.

*   Docker (probably [docker-desktop](https://www.docker.com/products/docker-desktop)), or
*   Any other container runtime + scheduler (K8s)
*   [Go](https://golang.org/) (K8s is written in Go)
*   Vagrant and Virtualbox (local dev)
*   [Python](https://www.python.org/)
  - [PyCharm](https://www.jetbrains.com/pycharm/) for development
*   [Node.js](https://nodejs.org/en/)
  - [VSCode](https://code.visualstudio.com/) for development
*   [Java](https://www.oracle.com/java/technologies/javase-jre8-downloads.html)


### Sites

*   None now, subject to change.


### Browsers

Generally we use Chrome, as it works well with GSuite, etc., but it’s good to have a variety installed for testing.

#### Extensions
*    [HTTPS Everywhere](https://chrome.google.com/webstore/detail/https-everywhere/gcbommkclmclpchllfjekcdonpmejbdp)
*    [uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm)
*    [Privacy Badger](https://chrome.google.com/webstore/detail/privacy-badger/pkehgijcmpdhfbdbbnkijodmdjhbjlgp)
