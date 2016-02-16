## Challenge 0
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

## Challenge 1
### Making a branch and making commits on it

1. Make a branch with `git branch new_branch_name`
1. Checkout (switch) to that branch `git checkout new_branch_name`

   _Note: Alternatively, use `git checkout -b new_branch_name` to do both in one command!_

1. Edit a file and make commit on that branch. Create a new file if you'd like!

   _Note: If you made a new file notice how you cannot use `git commit --all --message ""` to add and commit this new file in one step.  You'll first have to use `git add new_file_name`._

1. Check the logs to see your commit with `git log` or `git show` to only show the last commit!

## Challenge 2
### Merging your branch into master

1. Switch back to the master branch with `git checkout master`

   _Protip: `git checkout @{-1}`!_

1. Use `git log` or `git show` again to see that your commit isn't on master.
1. Merge your "other" branch into master with `git merge new_branch_name`
1. Read that whole log output. Use `git log` again and observe how your commit is now in master!
