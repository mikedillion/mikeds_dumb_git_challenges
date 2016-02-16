## Exercise 0
### Create some files and dump some text into them.

```
$ mkdir whatever                        # Create a working directory
$ cd whatever                           # Get inside if it
$ brew install lorem                    # Install this lorem thing
$ lorem -n 800 | split -b 2000 - file_  # Create three files of lorem ipsum
$ git init .                            # Create a new Git repo right here
$ git add *                             # Add all the files you just created
$ git commit --message "First Commit"   # Commit!
```

## Exercise 1
### Making a branch and making commits on it

1. Make a branch with `git branch new_branch_name`
1. Checkout (switch) to that branch `git checkout new_branch_name`

   _Note: Alternatively, use `git checkout -b new_branch_name` to do both in one command!_

1. Edit a file and make commit on that branch. Create a new file if you'd like!

   _Note: If you made a new file notice how you cannot use `git commit --all --message ""` to add and commit this new file in one step.  You'll first have to use `git add new_file_name`._

1. Check the logs to see your commit with `git log` or `git show` to only show the last commit!

## Exercise 2
### Merging your branch into master

1. Switch back to the master branch with `git checkout master`

   _Protip: `git checkout @{-1}`!_

1. Use `git log` or `git show` again to see that your commit isn't on master.
1. Merge your "other" branch into master with `git merge new_branch_name`
1. Observe how you changes are now in master! Read that whole log output.

## Exercise 3a
### Creating a merge conflict to look at!

1. Create a NEW branch from your current location (the HEAD of master) and
   switch to it.
1. Make a commit to a file that also exists in the `master` branch
1. Switch back to the master branch again.
1. Make some changes on same file and the same lines that you just did on the
   other branch.
1. TRY to merge the branch into master with `git merge your_other_branch_name`

## Exercise 3b
### Examining and resolving the merge conflict

1. Execute `git status` and observe that you have a new category.
   In addition to the usual "Changes to be committed",
   "Changes not staged for commit", or sometimes even "Untracked files" section
   you now have a "Unmerged paths" section.
1. Open the file that is listed under the "Unmerged paths" section and goto the
   section you have been changing.
   It should look somewhat like this:

```
<<<<<<< HEAD
Non lectus sagittis semper!?!?!?
=======
Non lectus sagittis semper!!!!
>>>>>>> your_other_branch_name
```

Where your changes are listed instead of:
```
Non lectus sagittis semper!?!?!?
Non lectus sagittis semper!!!!
```

1. Decide which line above or below the `=======` offends you less.
1. Delete everything else including the `=======`, `>>>>>>>`, and `<<<<<<<` lines.``
1. Use `git add the_file_name_from_the_unmerged_paths` to "stage" the file.
1. Run `git status` again and see how everything is back to normal!

## Exercise 4
### Rebasing with no problems

1. Go back to the branch you in the Exercise 1.
1. Run `git log` to see that it is just as you left it.
1. Make an edit to some file and commit those changes.
1. Execute `git rebase master` to:
    1. "rollback" this the branch to the most recent common commit it shares with the master branch.
    1. "add" the commits that follow that most recent common commit just as they appear on master.
    1. Finally, "replay" the commits that have been made on this branch that follow after the most recent common commit.
1. Observe with `git log` that I am not lying to you.

## Exercise 5
### Rebasing with conflicts and interactive rebasing.

Oh man, see me instead. Or request that I just finish this. I got bored.