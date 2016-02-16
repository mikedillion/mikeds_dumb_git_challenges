## Challenge 3a
### Creating a merge conflict to look at!

1. Create a NEW branch from your current location (the HEAD of master) and
   switch to it.
1. Make a commit to a file that also exists in the `master` branch
1. Switch back to the master branch again.
1. Make some changes on same file and the same lines that you just did on the
   other branch.
1. TRY to merge the branch into master with `git merge your_other_branch_name`

## Challenge 3b
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

## Challenge 4
### Rebasing with no problems

1. Go back to the branch you in the Challenge 1.
1. Run `git log` to see that it is just as you left it.
1. Make an edit to some file and commit those changes.
1. Execute `git rebase master` to:
    1. "rollback" this the branch to the most recent common commit it shares with the master branch.
    1. "add" the commits that follow that most recent common commit just as they appear on master.
    1. Finally, "replay" the commits that have been made on this branch that follow after the most recent common commit.
1. Observe with `git log` that I am not lying to you.
