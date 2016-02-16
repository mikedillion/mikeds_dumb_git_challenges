## Challenge 3a
### Creating a merge conflict to look at!

1. Create a NEW branch from your current location (the HEAD of master) and
   switch to it.
1. Make a simple change on one line of a file and commit that change.
1. Switch back to the `master` branch.
1. Make a change to the same file on the same line that you just did on the
   other branch.
1. Merge the branch into master with `git merge your_other_branch_name`
1. Read the output and don't freak.

## Challenge 3b
### Examining and resolving the merge conflict

1. Execute `git status` and observe that you have a new category.

   Where you might usually see "Changes to be committed",
   "Changes not staged for commit", or sometimes even "Untracked files" sections, notice that you now have an "Unmerged paths" section.
1. Open the file that is listed under the "Unmerged paths" section and goto the
   line you have been changing.

   It should look somewhat like this:

  ```
  <<<<<<< HEAD
  The quick brown fox
  =======
  The quick RED fox
  >>>>>>> your_other_branch_name
  ```

  Where your changes are listed instead of:
`The quick brown fox`
and `The quick RED fox`

1. Decide which line above or below the `=======` offends you less.
1. Delete the offending line and everything else including `=======`, `>>>>>>>`, and `<<<<<<<`.
1. Use `git add the_file_name_from_the_unmerged_paths` to "stage" the file.
1. Run `git status` again and verify that everything is cool.

## Challenge 4
### Rebasing without any problems

Our goal here is to simulate what happens when other work proceeds concurrently to your own. Pretend that the changes we made in Challenge 3 were done by someone else.

We are now going to change the starting point (where we initially branched from `master` in Challenge 1) to the current `HEAD` of the `master` branch. The commits that took place in Challenge 3 will appear before the changes committed in this branch and we're ready to merge there won't be any surprises!

Note that Git will let you merge changes that don't mix well together as long as those changes weren't to the same sections, or blobs. Imagine a group of politicians are working on a constitution together and two of the articles contradict each other! Oh no! Git doesn't care!

1. Checkout the branch you created in the Challenge 1.
1. Run `git log` to see that it is just as you left it.
1. Make an edit to a file that hasn't been modified since its creation in Challenge 0 and commit those changes.
1. Execute `git rebase master` to:
    1. "rewind" this branch to its original starting point.
    1. "update" that starting point to the current `HEAD` of the `master` branch.
    1. "apply" the commits that have been made on this branch.
1. Observe with `git log` that I am not lying to you.

The reason this step is called "Rebasing without any problems" is due to the fact that we were very specific about which file was modified in step 3. Since it wasn't modified in any of the previous Challenges we could guarantee that there wouldn't be any conflicts when rebasing.

Next we'll see what happens when changes are being made to the same files but in different branches.
