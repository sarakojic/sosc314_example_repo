This is intended to be a concise explanation of everything you need to work with GitHub. See also GitHub's own [documentation](https://docs.github.com/en/get-started/using-git/about-git).

### Git
To interface with GitHub, you need git installed. On Mac and Linux, you can do this with your package manager, and it may even be installed already. On Windows, download git for windows [here](https://gitforwindows.org/). For the installation, just leave everything at its default.

There's also a [version with a graphical UI](https://desktop.github.com/download/) that's easier to use. I recommend that you use this graphical UI.

### Authentication
Follow the instructions [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys). There is one version for each of Windows/Mac/Linux. You probably won't have a key yet, so then go through 'Generate new SSH key'. Either way, then do 'Add a new SSH key'. Finally, 'Test your SSH connection'.

### Basic use

#### Create a repository
Create a repo by going to https://github.com and click the green `New` button. Choose a name and tick the box to create a readme file, everything else can be ignored.

#### git clone
Create a local version (i.e. a copy of the folder that's hosted on GitHub) by clicking on the green 'Code' button in the repository. Make sure SSH is selected, then copy the path to your clipboard.

Then in your shell (Git Bash on Windows), navigate to the base directory where all your github repos are located. Then do git clone and paste in the path you just copied. For example `git clone git@github.com:markusneumann/sosc314_example_repo.git`. This downloads the contents of the repo onto your computer.

#### git status
`git status` tells you what's going on in your local copy of the repo. Importantly, it will tell you whether your local has changes the remote doesn't have, or vice versa. It will also show which files are not being tracked (as in, only in your local version, but not synced with the remote).

#### git add
When you've done some work in your local repo and you want to sync it to the remove, use `git add` and then specify the files to add. You can add multiple files like this:
`git add -A` (stages all files in your local repo) \
`git add -u` (stages all updated files) \
`git add folder/*` (stages all files in a folder) \

git add stages a file - it prepares it for sync.

#### git commit
Once you've staged all the files for a specific commit, you can make that commit by typing `git commit`. This will open a text editor so you can type a short explanation of what the staged changes do. 

If you are on Mac or Linux, it is possible the default editor is vi or vim, which can be a bit difficult to use because it has multiple modes. By default, you are in normal mode. To type something, press `a` to go to edit mode, then type your commit message. Then press `Esc` to go back to normal mode. Then press `:wq` to write and quit. Here's a [cheatsheet](https://devhints.io/vim) for vim.

You can also avoid entering an editor by typing your commit message in the command line like this `git commit -m 'this is a commit message'`.

When you do this for the first time, you may have to do something like this first (it will tell you when you try to commit): `git config --global user.email "mneumann.polsci@gmail.com"`

#### git push
Once everything is ready, use `git push` to actually sync your changes to the remote. If the remote has changes your local repo doesn't have, you will have to approve a merge (it will put you in the text editor - just save and quit) before you can push.

#### git pull
If the remote has changes your local repo doesn't have, you can use `git pull` to sync.

### Misc
#### Github-flavored markdown
The readmes in github repos use Github-flavored markdown. See [here](https://github.github.com/gfm/) and [here](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) for documentation.

#### Branches
Branches can be used to maintain different versions of the same code. This allows them to be kept separate mostly, but changes made to code in one branch can then also be applied to another (for example to fix a bug in both).

#### gitignore
To always ignore certain filetypes when adding, put their endings into a `.gitignore` file.

#### Issues
Github allows people to file issues against the repository, usually to file bug reports. We may use this to assign work.

#### Pull requests
If you think a repository that is not your own should a specific change, make a pull request

#### Wiki
Github allows you to create wikis. Such as this one ;-)

#### Settings
Repos have settings. Don't touch the red stuff ;-)

#### Troubleshooting
Here's a helpful resource that describes how to deal with common problems: https://dangitgit.com/
