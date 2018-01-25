# Switching to OpenRC

If you have any problems, ask for help on [our Discord server](http://discord.gg/2dcxvdF).

If you forked or cloned the ftc_app repository, follow the instructions for Git users.
Otherwise, you'll need to follow the instructions for non-Git users, even if you technically
do use Git.

## I have a Git repository that includes the full history of ftc_app
These instructions assume that you have Git available on your PATH. If that's not the
case, you'll get some kind of `command not found` error when you try to follow these
instructions. If that happens, install Git using
[these instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git),
and then restart Android Studio.

1.  Set up your remotes. 

    a.  Note that the list of remotes is not synced using Git, so you should do this on any
        computers that have a copy of this repository.
    b.  Open the Terminal tab in Android Studio.
    c.  To see your current remotes and where they point, enter the command
        `git remote -v`.
    d.  Your `origin` remote should point to wherever you're hosting your repository.
        You probably have a remote (usually named `upstream`) that points to the
        official FTC repository (`https://github.com/ftctechnh/ftc_app.git`). 
    e.  Delete whatever remote points to the official FTC app. For example, 
        `git remote remove upstream`.
    f.  Replace it with an `upstream` remote that points to whichever version of OpenRC
        that you prefer. If you want to have access to Blocks and OnBotJava, use the
        command `git remote add upstream https://github.com/OpenFTC/OpenRC.git`.
        If you don't care about those features and you want the app to deploy faster,
        use the Turbo version, with the command
        `git remote add upstream https://github.com/OpenFTC/OpenRC-turbo.git`.
2.  Pull from the OpenRC remote you just set up: `git pull upstream master`.
3.  Resolve any merge conflicts. The most common reason for these is that you've
    added additional modules to the project. My preferred way to do this is by selecting
    `VCS > Git > Resolve Conflicts` from the menu bar in Android Studio. You'll need to
    have Git set up and enabled in Android Studio for this to work.
    ([See here](https://www.jetbrains.com/help/idea/using-git-integration.html).)
4.  If you had any merge conflicts to resolve, you'll have to commit to finish the merge.
5.  You're done! In the future, you can update to new versions of OpenRC with the command
    `git pull upstream master`.


## I don't use Git
This option is not recommended if you might make any modifications to the app outside of
the TeamCode folder, since those changes will be overwritten every time you update OpenRC.
Instead, make a new fork of OpenRC and start using Git.

1.  Close Android Studio

2.  Make a copy of your FTC app folder as a backup. This is especially important if you've made any changes
    outside of the `TeamCode/src` folder.

3.  Download the zip file of the current master branch of your chosen OpenRC variant.  
    [Direct link for Standard](https://github.com/OpenFTC/OpenRC/archive/master.zip)  
    [Direct link for Turbo](https://github.com/OpenFTC/OpenRC-turbo/archive/master.zip)


4.  The zip file has a folder inside with the name of the repository. Extract the contents
    of _that_ folder to your current FTC app folder. The idea is that you're overwriting all
    of the official files with ones from OpenRC. Your OpModes will remain intact of course.

5.  If you've modified any files that got overwritten, you'll need to re-modify them. You can use the files
    in your backup folder as a reference.
