# Changing Commit Messages

If you have already pushed the commit to GitHub.com, you will have to force push a commit with an amended message.

We strongly discourage force pushing, since this changes the history of your repository. If you force push, people who have already cloned your repository will have to manually fix their local history. For more information, see the [official docs from GitHub](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message).

---

## Steps

In the Terminal, type:
- `git rebase -i HEAD~#`

(replace the `#` with the number of previous commits you want to show)

Example:
- `git rebase -i HEAD~5`

For each commit message you want to change, replace the word `pick` at the start with `reword`.

Example:

```
pick 8f6e755 Update README with automatic updates on username
pick af3bed3 Add boilerplate for index page
reword cb6e4ec Update index with starter header/nav elements, and add some code comments, and this commit is intentionally long on purpose in order to try to change the commit message later
pick f06170d Add starter CSS styles
reword 6c2f44a Add footer details and link to CSS
```

*As you can see, I've selected two previous commit messages to `reword`.*

Save the file, and then close it.

For any commit you've selected to `reword`, once you've saved/closed the file, it'll launch a new commit file to edit the message.

Example original commit:
- `Update index with starter header/nav elements, and add some code comments, and this commit is intentionally long on purpose in order to try to change the commit message later`

It will show in red text if too long, or white text if already less than 50 characters.

Edit this to what you want the new commit to be.

*(note: it gives you a vertical grey line to remind you of where 50 characters is for the max-length per line)*

I've updated the red text to:
- `Update index with starter header/nav elements with code comments`

Save the file, then close it.

This process will repeat for any other commits that you selected for `reword`.

Repeat, save/close for each of them until all of your reword commits are done.

Once they're all saved and closed, it'll bring you back to the Terminal.

Now, all we need to do is "**force**" push these changes.

**Please note: we should, where possible, avoid force-pushing! Use this with caution!**

- `git push --force`

That's it!
