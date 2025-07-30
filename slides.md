---
# You can also start simply with 'default'
theme: seriph
colorSchema: auto
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Git Good
download: false
info: false
author: Sheron Rajesh
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
seoMeta:
  # By default, Slidev will use ./og-image.png if it exists,
  # or generate one from the first slide if not found.
  ogImage: auto
  # ogImage: https://cover.sli.dev
---

# Git Good

Getting started with Git and GitHub

<!--
We will be discussing

- Version Controld
- Git
- Why Git
- GitHub
- Why GitHub

And we will be learning a bit of Git and GitHub just to get you started on collaborating

And this discussion will be interactive, and you'll all be collaborating me on this slides.
-->

---
layout: section
---

# Why These Tools?

<v-click>Keeping track of changes is hard.</v-click>

<!--
# layout: image
# image: final-doc.png
# backgroundSize: contain
-->

---

# Why is it so hard?

- Keeping track of changes across multiple versions of a file
- Working with others without overwriting each other's work
- Figuring out who did what, and when
- Reverting (undo) to an older change
- Trying out new things without breaking the main system

---

# Version Control

<v-clicks>

- Maintains a complete history of every change
- Allows multiple people to collaborate safely
- Experiments without risk by branching
- Easily revert mistakes
- Compare changes

</v-clicks>

<h2 v-click>Especially in the software world, it was really difficult to keep track of changes with all the code, <span v-mark.underline>busg</span> and fixes.</h2>

<br /> 
<h2 v-click>Much more difficult in the open-source world.</h2>

---
layout: section
---

# Linux

<v-click>Linus Torvalds 👑</v-click>

---
layout: section
---

# Git

<v-click>Version Control System (VCS)</v-click>

---

# Git

<span>Now you know what Git is used for.</span>

<v-clicks>

So,

- Open source, free
- VCS (Version Control System)
- Distributed, works locally
- Checkpoints
- Time machine like: track, revert, go back
- Collaborations
- Branch out, and experiment without breaking.

</v-clicks>

---

# GitHub

- Kind of like a storage, but not just that.

- Platform for sharing and hosting Git repositories

- Store local Git repositories online, and keep them synced

- Issues, feedbacks, comments, forks

- Review code, suggest changes, pull requests

- Makes collaboration easier

---
layout: quote
---

# https://git-scm.com/downloads

Once installed, open your terminal and try running:

```bash
git --version # should print the version
```

Setup your user:

```bash
git config --global user.email "name@example.com"
git config --global user.name "My name"
```

---

# Familiarizing Terms: Part I

- **Repository (repo)**: Basically project folder. Can contain anything that your project needs

---

# Let's try out Git

Open your terminal.

Create a folder first:

```bash
mkdir git-good # or whatever your project name maybe
```

Go to that folder:

```bash
cd git-good
```

Let's make this folder a Git repository:

```bash
git init
```

Now, if you run the following, you should see a folder named `.git`, meaning, this is now a <span v-mark.underline>Git repository</span>

```bash
ls -a
```

<style>
  code {
    font-size: 1.1rem;
  }
</style>

---

## `git init`

Initializes a Git repository in the current working directory.

It creates a `.git` folder where all the information regarding version control lies.

---

Now let's create a file in this repository.

```bash
touch file.txt # or anything
```

Let's open this file in an editor of some sort and add some content.

```plaintext [file.txt]
Hello
TinkerHub
World
```

Tell Git to track this file for changes from now on:

```bash
git add file.txt
```

Let's make sure it's now staged.

```bash
git status
```

<style>
  code {
    font-size: 1.1rem;
  }
</style>

---

# Checkpoints

<v-clicks>

- The `file.txt` is now tracked by Git.

- Content maybe <span color="green">added</span>, <span color="yellow">modified</span>, or <span color="red">removed</span>.

- To compare later, commit the changes.

  ```bash
  git commit -m "create file for testing"
  ```

- Make changes &rarr; Add changes &rarr; Save changes

- work &rarr; stage &rarr; commit (in Git terms)

- Check tree status & log:

  ```bash
  git status # should say clean.
  git log # use `q` to quit.
  ```

</v-clicks>

<style>
  code {
    font-size: 1.1rem;
  }
</style>

---

# Activity I

1. Make changes to the file, or try creating another file.
2. `git add` those modified files.
3. `git status`
4. `git commit -m "commit message"`
5. `git log`

<br />

<v-click>
Now, make more changes to your files.

Before `git add`, try `git diff`

```bash
git diff
```

It shows the changes you have made to your file.
<b color="green">+</b> (plus) shows added lines, <b color="red">-</b> (minus) indicates removed lines.

If you have modified a line, it will show as both <b color="green">+</b> and <b color="red">-</b> for it, because Git shows line-by-line change.

</v-click>

---
layout: quote
---

# https://github.com

Create an account and login if you already haven't.

<v-click>

1. Go to your dashboard.
2. Create a new repository and name it.

</v-click>

<!--
Mention gh
-->

---
layout: quote
---

# https://cli.github.com

Command line for GitHub, easier authentication.

<v-click>

Connect your GitHub account with Git.

```bash
gh auth login
```

Authorizes and gives your local machine to access your account.

</v-click>

<style>
  code {
    font-size: 1.1rem;
  }
</style>

---

# Pushing your code to GitHub

Hosting your code.

This connects the GitHub repository as your remote origin.

```bash
git remote add origin [url-to-your-github-repository]
```

```bash
git branch -M main # renames your branch `main`
git push -u origin main # pushes the `main` branch to GitHub origin
```

<style>
  code {
    font-size: 1.1rem;
  }
</style>

<!--
Showcase issues, and other stuff
-->

---

# Branches and Pull Requests

<v-click>

- I'm naming my new branch `some-changes`

- Create and switch to the branch:

  ```bash
  git branch some-changes

  git checkout some-changes # `git switch` also works
  ```

- Make some changes.

- Add (stage) and commit the changed files.

- Push to the remote repository using:

  ```bash
  git push -u origin some-changes
  ```

</v-click>

<style>
  code {
    font-size: 1.1rem;
  }
</style>

<!--
Show pull request, files, merging
-->

---

# Collaborating

<v-clicks>

1. Forking (GitHub term)

2. Cloning using `git clone`
3. Branching out (if needed)
4. Pushing to your own copy
5. Requesting to merge your changes

</v-clicks>

---
layout: quote
---

# https://github.com/dcdunkan/good-git

1. Fork to your own account

2. Clone the forked repo to your system

```bash
git clone https://github.com/[your-username]/good-git
```

<style>
  code {
    font-size: 1.1rem;
  }
</style>

---

# Activity II

1. Go to the fork-cloned repository folder.
2. Create a new branch under your username and switch to it.
3. Open the `attendees` folder.
4. Create a file with your username on it ending with `.md` extension.

5. Add literally anything that you want.

6. Check out `attendees/dcdunkan.md` for reference.

7. Open `people.md` file.

8. Add the following to it:

```
---
src: ./attendees/<username>.md
---
```

9. Add, commit, push to your branch, and make pull request.

---
src: ./people.md
---

---
layout: center
class: text-center
---

# Thank you

<PoweredBySlidev mt-10 />
