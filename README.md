# Git-Flow


Git is an essential tool for developers. It's widely used in the world of open source and at most organizations.

## Objectives

- Initialize a git repository to track changes.
- Create a new branch to isolate your changes.
- Add new or modified files to the staging area for committing.
- Remove files from the staging area before committing.
- Commit new and modified files to a git repository.

## Why Git

Version control is important for developers. We need to store our code safely and track changes as we make them. If we introduce a feature that breaks our application, we want to be able to revert back to a working state.
![why git](https://www.git-tower.com/learn/media/pages/git/ebook/en/desktop-gui/basics/what-is-version-control/5bcefb6718-1682408980/what-is-vcs.png)

## Making a Local Repository

Let's initialize a local repository.

1. In your `studies` repository, reate a new directory named `<your-name>s-game-of-gits` inside your `~/sei/trainings` directory.

2. Inside the `<your-name>s-game-of-gits` directory, create a file named `sad-tale.md`.

3. Open the `sad-tale.md` file with VS Code and paste the following lines:

```text

House Stark of Winterfell is led by the just Eddard "Ned" Stark, Lord of Winterfell, 
Warden of the North, Hand of the King, Protector of the Realm, Regent. 
He is surely honorable and will lead a long and prosperous life.

```

4. Save the file.

5. In the `<your-name>s-game-of-gits` directory, run the command `git status`. Did anything happen?

6. Run the command `git init` in the `<your-name>s-game-of-gits` directory.

7. Run the command `git status` again. Did anything happen this time?

## Staging and Committing

We will use the command `git add <name-of-file>` to stage our story for committing.

There are 3 states that a file can reside in: `modified`, `staged`, and `committed`. These states correspond to different sections of a Git project.

- Modified: You have made changes to the file but have not committed them to your git repository yet.
- Staged: You have marked a modified file in its current version to be included in your next commit snapshot.
- Committed: The data is safely stored in your local git repository.

For more information, refer to the [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) guide.

![Git Sections](https://git-scm.com/book/en/v2/book/01-introduction/images/areas.png)

When we add a file, we move it from the working directory to the staging area.

Now that our file is staged, let's commit it by typing `git commit`. This will open VS Code.

## Crafting A Commit
### Exercises

Read the blog post [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/) and think about what would be a good commit message for your changes. Take your time to come up with your own commit message. You will share your commit with the rest of the class.

After making our first commit, let's see what happens when we type `git log`... We will see our previous commit! The `git log` command typically shows all of our previous commits, but since we only have one, that's all we will see. Feel free to explore different options for `git log`, such as `--oneline`, `--name-status`, and `--relative-date`. You can find more options [here](https://git-scm.com/docs/git-log).

## Staging: And He Lived Happily After

Let's continue our story in the `sad-tale.md` file.

Copy the following text and paste it after the current contents of our story, then save the file:

```text
Ned Stark went to King's Landing where he made lots of 
friends and lived happily ever after... He definitely 
didn't get axe-murdered.
```

Now, using the knowledge we learned earlier, stage this change. To check the status of your files, you can always run `git status` in the terminal.

> ### :triangular_flag_on_post: Remember: Staging isn't committing

## Unstaging: Maybe We Jumped the Gun

Unfortunately, it turns out that Ned did get axe-murdered. So, let's unstage our file.

To unstage the file, use `git reset <filename>`.

Also, let's delete the last thing we wrote in `sad-tale.md`.

## Removing: Deleting Staged Files

Let's practice removing files after they have been staged.

### Using The Bash `rm` Command

1. Inside the `<your-name>s-game-of-gits` directory, create a file called `the-stark-bunch.md`.

2. Open the file with VS Code and copy the following lines:

```text
This is a story... of a man named Neddy... and three very badass really awesome girls.
```

3. Save the file.

4. Run `git add the-stark-bunch.md`.

5. Run `rm the-stark-bunch.md`.

6. Run `git status`.

What do you see? The addition of `the-stark-bunch.md` is still staged as a `new file` type change, but there is also an unstaged `deleted` type change. You need to run an additional command to unstage the `new file` change.

7. Run `git reset -- the-stark-bunch.md`.

### Using The `git rm` Command

1. Inside the `<your-name>s-game-of-gits` directory, create a file called `the-stark-bunch.md`.

2. Open the file with VS Code and copy the following lines:

```text
This is a story... of a man named Neddy... and three very badass really awesome girls.
```

3. Save the file.

4. Run `git add the-stark-bunch.md`.

5. Run `git rm -f the-stark-bunch.md`.

6. Run `git status`.

What's the difference between `git rm` and `rm`? What is actually happening with the `git rm` command?

## Branching: Multiple Stories, One Main Plot

Let's create a dream-story branch and write an alternative ending for Ned's story.

1. Create a branch called `dream-story` by typing `git branch dream-story`.
   _(You can see all your current branches at any time by typing `git branch`.)_

   > You can also create and switch to a branch at the same time by using the
   > `-b` flag! (`git checkout -b dream-story`)

2. Switch to your `dream-story` branch and write a brief description of what
   you would have wanted to happen to Ned.

3. Save the file, stage and commit your changes.

4. Switch back to your `main` branch. (Notice anything?) Add what really
   happened to Ned.

5. Stage and commit your changes.

(Be ready to talk about any issues you may have encountered or strange things
you may have noticed.)

## Git Workflow Checklist

- [ ] Use `git status` to confirm a clean working directory.
- [ ] Confirm that you are on the correct branch.
- [ ] Make changes to the file.
- [ ] Use `git add 'file'` to stage the changes.
- [ ] Use `git status` to confirm that the modified files have been staged.
- [ ] Use `git commit` to commit the changes.
- [ ] Use `git log` to verify that your last commit worked.

You can use the [git cheatsheet](./git-commands.md) at any time.

## Git Best Practices

Here are some best practices to follow when using Git:

- **ADD files explicitly:** When staging files, use full paths to refer to each file explicitly. For example, `git add foo/bar.md baz/qux.js`. This ensures that you only stage the intended files.

- **AVOID `git add .`:** Unless you have just initialized a new repository and need to stage all the files, it's best to avoid using `git add .`. This command stages all the files in the current directory and its subdirectories, which can lead to accidentally staging unwanted files.

- **ALWAYS use `git status`:** Before executing any other Git command, it's good practice to run `git status` to check the current status of your repository. This helps you understand what files have been modified, staged, or committed.

- **NO commit is too small:** It's recommended to make commits that are focused and contain logical changes. Even small changes or fixes should be committed separately, as it helps in tracking the history and understanding the evolution of your codebase.

- **NO commit message is too long:** Take the time to write descriptive commit messages. Explain the purpose of the changes, the problem they solve, or any relevant context. A well-written commit message makes it easier for others (including your future self) to understand the changes later.

- **NEVER nest repositories:** It's important to avoid nesting repositories within each other. This means that you should not create a Git repository inside another Git repository. Nesting repositories can lead to conflicts and make the history and management of your codebase more complex.

Following these best practices will help you maintain a clean and organized Git workflow.





