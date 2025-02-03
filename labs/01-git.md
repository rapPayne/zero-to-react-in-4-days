# git Lab

## Clone the repo
We're assuming you have this repo because your instructor walked you through the process of cloning it. If not, do that now.
```bash
git clone https://github.com/rapPayne/zero-to-react-in-4-days.git --recurse-submodules
```

## Get the data server running
1. Establish an upstream repo where your code for these labs will be held.
1. Clone this upstream repo to a local repo on your development machine.
1. In that folder, create a README.md file with a few notes about your project.
1. Get the API data server running on your local machine by copying the entire [server](../server) folder to your project and running these three commands in your new server folder:
```bash
npm run load-db
npm run start
```
1. git add, git commit, and git push it up to the upstream repo.
1. Verify that your changes are present in the upstream repo.

## Merge conflicts
1. In your local repo, make a change to a particular sentence in your README.
1. Git add and commit it but do not git push it.
1. In another folder, clone your project from your upstream repo.
1. Make a *different* change to that same sentence in your README.md
1. Git add, commit, and push.
1. Now back in the original folder, git pull.
1. You'll see that there is now a merge conflict.
1. Edit the README file. Resolve the conflict by including some features of both changes.
1. Git add, commit, and push.

## Automate the CI/CD pipeline
1. Ola will help us to deploy it.

In all of the following labs, make sure you commit changes to git and push them to your upstream repo.