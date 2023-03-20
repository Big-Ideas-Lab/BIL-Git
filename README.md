# Big Ideas Lab Git Instruction and Best Practices

## Introduction

## Feature Branch Workflow

The instructions below were adopted from a standard feature branch workflow that you can read more about in this [article](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow). This workflow is adjusted to work with the typical team size and collaboration needs in the lab, but feel free to adapt a variation or another workflow (e.g. Centralized Workflow) if it fits your project better. 

### Clone the Project

1. On your local machine, navigate to the directory where you want to store the project. 
> **Note:** Make sure that your parent directory does not have git initiated from another project. A good separation from your other tasks are recommended.
2. In that directory, clone the repository with `git clone <project-url>`.
```
git clone git@github.com:billchen0/BIL-Git.git
```
3. Follow setup instruction on that specific project's README.

### Development
1. (Situational) If your team member recently merged a pull request to the main branch, run `git pull` to make sure you have the latest update.
2. Create your feature branch with `git branch <feature-name>` 
3. Checkout to your feature branch with `git checkout <feature-name>`
4. Once you finish a modular section of your code (an endpoint, a component, a view, a function, etc.), add your files to the staging area with `git add <filename>`
5. Commit your changes with `git commit -m "<commit message>"`
6. After every working session, push your code to GitLab from local with `git push`
7. Once you are fully compelted with your feature branch, start a merge request in GitLab and select your reviewer. 

### Rebasing
Whenever a feature branch from your teammate was merged into main through a pull request, you will have to rebase the feature brances you are currently working on. 

<p align="center">
<img src="https://www.blog.duomly.com/wp-content/uploads/2020/05/Rebase.png" width="200px"></img>
</p>

1. To perform rebase, run the following command on your feature branch `git pull --rebase origin main`.
2. If there are merge conflicts, resolve them and then re-stage your files with `git add <filename>`.
3. Run `git rebase --continue` to complete rebase (Note: Do NOT run `git commit` during rebasing).
4. When rebase is completed, run `git push --force-with-lease` to push your local branch to remote. (Note: NEVER run `git push --force` or `git push --force-with-lease` on the main branch)

### Merge Conflict

The easiest way to deal with merge conflicts are not to create them. This means communicating well with your fellow teammates so that you are not editing the same scope of program in your respective feature branches. Resolving merge conflicts are typically very situational, so if you encounter a situation not described below, please contact us!

1. If you encounter a merge conflict when merging code from remote to local, resolve the merge conflict manually in your IDE and run `git add <filename>` followed by `git commit -m "<commit-message>"` to register the resolved merge conflict. 
2. If you encounter merge conflict when performing a merge request on the GitLab GUI, resolve it in the interactive window and continue with merge request as prompted. 

If you are unsure of how code should be merged, please don't hesistate to contact the admin team to get suggestions. 

## Best Practices
