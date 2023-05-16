# Forking a PrairieLearn course for local development

It takes a lot of trial and error to get the hang of developing questions on PrairieLearn, particularly if you are algorithmically randomizing the questions.
From experience, the best way to develop questions is to have access to a demo course of your own so you can see exactly how the questions are rendered, and what tweaks need to be made to improve how the questions are displayed.

To get your own PrairieLearn course for local development, follow these steps:

## Step 1: Visit the [IND 100](https://github.com/open-resources/pl-opb-ind100) course repository I've created for you.

<img src="pl_images/ind100.png">

## Step 2: Fork the IND 100 repo into your **personal GitHub account**.

<img src="pl_images/ind100_fork.png">

## Step 3: Clone the IND 100 repository locally

```{warning}
For best results, you should clone your `IND 100` course repository in the same directory your cloned `instructor_physics_bank`.
```

Open a Terminal, navigate to the directory you want to clone the IND 100 course:

```
git clone git@github.com:open-resources/pl-opb-ind100.git
```

<img src="pl_images/ind100_clone.png">

Once you've got the repository cloned locally, you can [use Docker to continue course development](docker_course_dev).

## Updating the IND 100 repository

Once you fork the repository, you will be working on your own repository (with its own history, branches, commits, issues, pull requests, etc...).
Occasionally, we will update the IND 100 course as new features are implemented and added to the OPBs and to PrairieLearn.
The easiest way to update your fork, is to use GitHub's "Sync Fork" feature:

<img src="pl_images/ind100_sync_fork.png">

### Update `problem_bank_helpers`

Though the "Sync Fork" feature will address most things, it's also useful to know how to update custom python packages on PrairieLearn, such as the `problem_bank_helpers` package.
Each course that uses an OPB requires the `problem_bank_helpers` to be installed within the `serverFilesCourse` directory.
More details about this are in the [PrairieLearn documentation](https://prairielearn.readthedocs.io/en/latest/questionRuntime/#installing-libraries-in-your-course)

Here's how we can use pip to install the package:

```
pip install --target serverFilesCourse/ problem_bank_helpers
```

To update this package, we just need to add the `--upgrade` flag:

```
pip install --target serverFilesCourse/ problem_bank_helpers --upgrade
```

That should be it!

```{tip}
Remember to add, commit, and push the changes so the repository is updated correctly.
```