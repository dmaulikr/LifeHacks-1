# How to use GitLab

## 1. Install Git on your computer

### Linux

Setting up the necessary tools should be easy as most Linux distributions include the necessary tools like SSH, Git (and a browser) in default software selections.

### Install Git on Windows

In order to work with **Git**, you'll need to install [Git SCM for Windows](http://git-scm.com/download/win) on your machine. If you click on the link, the download should start automatically. However you must agree on running the Windows installer on your computer to be able to proceed.

You'll be asked to select various options during the installation process. They may sound a little arcane. Here is the default setup we recommend:

- _Acknowledge the license_ with "Next"
- _Select destination location_: the default PATH is fine, click "Next"
- _Select Components_: defaults are fine, click "Next"
- _Setup the start menu folder_: the default is fine, click "Next"
- _Adjusting your PATH environment_: choosing the option **Use Git from the Windows Command Prompt** will allow you to use `git` commands from the Windows CMD prompt and from the _**Git Bash**_, we recommend using this option, click "Next"
- _Choosing HTTPS transport backend_: Select **Use OpenSSL library**, click "Next"
- _Configure line ending conversions_: **Checkout Windows-style, commit Unix-style line endings**, click "Next"
- _Configuring the terminal emulator to use with Git Bash_: **use MinTTY**, click "Next"
- _Configuring extra options_:
  - Unselect **Enable file system caching**
  - Select **Enable Git Credential Manager**, click "Next"
- _Configuring experimental options_: leave unselected, click "Install"

Now the installation will proceed, at the end select **Launch Git Bash** and click "Finish".

### Mac OS

Git comes with the Xcode developer tools. If you are developing on your Mac you already have Git. If not,
download Git from [https://git-scm.com/download/mac](https://git-scm.com/download/mac).

## 2. Generate your SSH key pair

The SSH keys are used by Gitlab to authenticate you as developer and allow the synchronization of the repositories between your machine and the remote branches.

**For Windows users:** Git for Windows comes with its own Unix-like shell - the _**Git Bash**_. All commands shown below shall be entered in this shell. When starting _**Git Bash**_ for the first time, an environment for the current Windows user will be created automatically. You can type `whoami` to verify that you're using the right account. The current working directory is called `$HOME`, normally it is located on the `C:` drive under `/User/$USERNAME`. Typing `pwd` will show you the current working directory using the Unix path convention: `/c/User/$USERNAME`.

Now you can generate the required pair of SSH keys:

``` sh
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/$USERNAME/.ssh/id_rsa): #Press enter to save you keys at the default location
Enter passphrase (empty for no passphrase): #Enter a passphrase to protect your private key
Enter same passphrase again: #Once again
Your identification has been saved in /c/Users/$USERNAME/.ssh/id_rsa.
Your public key has been saved in /c/Users/$USERNAME/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256: **** $USERNAME@$HOSTNAME
```

That's it: now you can use the public key available under ~.ssh/id_rsa.pub (`/c/Users/$USERNAME/.ssh/id_rsa.pub` for Windows) to authenticate your local account against any remote server using the SSH protocol.

You can give this key to anyone who needs it - think of it as your ID card that you use to identify yourself to a server.

_**DO NOT share your private key with anyone, ever.**_ Think of your private key as the PIN on your ATM card.

## 3. Your first commit

NOTE: The actual process of working with `git` is out of scope for this How-To. There are many resources available - see the end of this guide for some we like. This section just covers basic Git setup.

First of all, configure your local git client to use your name and E-Mail address to sign the commits:

``` sh
git config --global user.name "Firstname Lastname"
git config --global user.email "your_email@gmail.com"
```

For this step, you will need at least **developer access** to a project. There are two ways to get this - either you get the needed rights from one of the project maintainers - or you _**fork**_ the project to your own space. Now clone the project as explained in the section "4. Checkout a project".

Let's assume you have developer access to the project and want to work on some changes in the code. The normal way of doing it using `git` is by creating a feature branch. To do so, you first need to change your working directory and use the `branch` command:

``` sh
cd code
git checkout -B feat/my-first-commit
Switched to branch feat/my-first-commit
```

Now pick any file, and make a useful edit using your preferred code editor. When you're done, save the file. In your terminal
verify that `git` is aware of the changes to that file:

``` sh
git status
On branch feat/my-first-commit
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

      modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Now add and commit your changes to the new branch:

``` sh
git add README.md
git commit -m "docs: my first commit"
```

To push your changes to the **remote git server**, you will need to set the branch upstream:

``` sh
git push --set-upstream origin feat/my-first-commit
```

Your changes are now available in the branch `feat/my-first-commit` of the project and you will see your commit on the top of your project list. To integrate your final changes to the `master` branch, you can create a **merge request**.

## Getting help on using Git

There is plenty of documentation, tutorials and online courses about `git` available. Here is a non-exhaustive list of documentation we find helpful:

- [git - the simple guide](http://rogerdudler.github.io/git-guide/)
- [git book - the complete documentation](https://git-scm.com/book/en/v2)
- [git tutorials from Altlassian](https://www.atlassian.com/git/tutorials)
- [git cheatsheet](http://ndpsoftware.com/git-cheatsheet.html)
- [Git for Ages 4 and Up - YouTube video](https://www.youtube.com/watch?v=3m7BgIvC-uQ)
- [How to use Git and Github - a free online course](https://www.udacity.com/course/how-to-use-git-and-github--ud775)
- [trygit - interactive tutorial](https://try.github.io/levels/1/challenges/1)

## More Commands

### Clone a Branch 

```
git clone -b <branch> <remote_repo>
```
Example:
```
git clone -b my-branch git@github.com:user/myproject.git
```
