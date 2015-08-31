# git-journal
## journalling project development with the power of git.

Tired of piles of notes spread across txt files, emails and TODOs?
With git-journal you can organize your ideas in a neat way that:

* Tracks history
* Allows you to make branches and not forget about what you've done before
* Trace back your though process
* Merge successive ideas into mainstream
* Whole lot of possibilities that git gives you

Installation
------------


Usage
-----

Setup journal for your git repo

	git journal init

This will create "journal" directory inside your repo and add "journal" section
to your repo config (not global, of course).

If you already have "journal" dir you can supply differen name like "notes" this
way:

	git journal init notes

"journal" directory is a git repo itself and it is not tracked by your parent
repo, so you don't have to modify gitignore.

The new commands for "journal mode" of git are:

* git journal add
* git journal edit

These are just wrappers around "git commit" with some sanity checks.

Adding a new record to your journal is a simple

	git journal add

This will invoke a text editor where you can write and edit a message.

Journal records are commits inside "journal" repository with a notable
exceptions:

* It does NOT change containing parent repo
* It does NOT create any files (there are no tree objects)
* It's a same old git history that you can play with

If your project got a new side idea just go to "journal" repo and branch!

	cd journal
	git checkout -b what-if

Later you can merge it back as usual

	git checkout master
	git merge --no-ff what-if


