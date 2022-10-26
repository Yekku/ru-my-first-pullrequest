# Heading 1

7 Git Best Practices to Start Using in Your Next Commit

1. Don’t git push straight to master. Branch it out!

```text
One of the features of decentralization is cheap branching. Pushing code straight to the master branch doesn’t promote collaboration. Git made simple comparing code between two branches, which can ignite healthy discussions, improve codebase quality, and spread the knowledge among developers. This practice has the name of Code Review.

To create a branch, run git branch -b <branch_name>. The command git branch -a lists all the available branches, and you can navigate among them using git checkout <branch_name>. A cool trick is to use git checkout - to switch back to the previous branch.
```

1. Adequately configure the commit authorship.

```text
You should at least set your name and email address correctly. As commits are communications tools, knowing who made a specific change can help you in the future.

Run git blame <file_name> to list line by line:

the last commit that changed it
the author of the commit
the timestamp of the commit
Don’t use it to blame someone, though. It won’t solve any problem. Therefore, you can ask the author about business contexts or technical motivations around that line of code. It may accelerate a bug fix, or trace from which commit that bug is present in the codebase.
```

1. Write descriptive and meaningful commit messages.

```text
As stated before, commits are communication tools. So, take your time to write a descriptive and meaningful commit message. Your future self and your team workers will thank you a lot.

Through the command git log, you can navigate through codebase’s history. They should tell you a story. Committing vague and abstract messages like “Bugfix”, or “Refactoring auth” may be a problem sooner than you think.

I enjoy writing a headline for the commit in the first line. Then, like it is an article, I would write essential pieces of information. I strongly recommend Chris Beams’s article on how to write a git message.
```

1. Commit only related work

```text
Do you know what S from SOLID stands for? Yeah, Single Responsibility Principle. You can apply this principle for commits, not only to the code. You should commit the least amount of lines that make sense together.

This practice helps when digging into the codebase, like when using git log or git blame.
```

1. Avoid rewriting the master’s history.

```text
One of the magic tricks git performs is the ability to rewrite log history. You can do it in many ways, but git rebase -i is the one I most use. With this command, It’s possible to switch commits order, remove a commit, squash two or more commits, or edit, for instance.

It’s particularly useful to run it before opening a pull request. It allows developers to “clean up” the mess and organize commits before submitting to review. If you follow the practice 3 and 4, then the list of commits should look very similar to a task list. It should reveal the rationale you had, telling the story of how you end up with that final code.

However, using git rebase in published branches, like the master, may generate lots of conflicts for the other contributors, which wastes lots of work can and hours of debugging when rebasing is frequent.

When you rewrite the history, you need to push with git push --force. To prevent a disaster, I always make sure to explicit the target branch. It avoids rewriting incorrect target branch’s history and an unnecessary headache to recover it. Avoid doing it to any published branches. Don’t hesitate to do it in your local branch, though.
```

1. Rebase your working branch frequently.

```text
It’s crucial always to keep your branch rebase with the latest code. Writing new code upon obsolete one is useless. It is as meaningless as fixing a bug that may already be fixed.

You should rebase your working branch frequently to prevent bugs, rework, and the tedious job of resolving conflicts with the upstream branch. You can do it easily by running these commands:

git checkout <upstream_branch>
git pull
git checkout -
git rebase <upstream_branch>
A cool trick is using git fetch --prune. It doesn’t require you to checkout to the upstream branch to update it. I love it.

1. Know the tool. Don’t be afraid of using it
```text
As I said, git is powerful. There are tons of commands. You can learn new tricks reading git docs on the web or using the man pages. By running git help -a,  you can check the most useful ones.

Here is a list of the ones I use very often:

git cherry-pick
git diff and git apply
git stash
git bisect
```

## Heading 2

Final thoughts

The list of 7 git best practices is not definitive. However, I think it’s very comprehensive and doesn’t depend on anyone else to adopt them. You can apply them immediately in your next commit.

I hope you enjoyed the content. Thanks for reading.
