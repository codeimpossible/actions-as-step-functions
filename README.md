# wip-actions-step-functions
Example of configuring actions as step functions to do a set of sequential operations

Create a PR adding your github username (ex: `codeimpossible`) to the [CONTRIBUTORS.md](./CONTRIBUTORS.md) file and check back in a minute or two after the PR is merged.


## What does this do?

There are three actions setup in this repo that automate the process of replacing the contributors username with their profile image.

| Action Name | Trigger | Description |
|-------------|---------|-------------|
| get-profile-image.yml | Runs when `CONTRIBUTORS.md` is changed | Reads all the lines without `<img`s and downloads the github profile for the matching username. The profile images are then committed back into the repository under the `/portraits` directory. |
| update-contributors.yml | Runs when any `*.png` is updated in master | This action runs over each changed PNG file and inserts them into the `CONTRIBUTORS.md` replacing the matching username. |
| remove-contributor.yml | Manual | This action is run manually and is used to remove a particular username portrait and entry from the `CONTRIBUTORS.md` |

## Configuration and Setup

By default, actions that commit into a github repository don't trigger other actions. This makes it hard to have one action trigger another. To get around this, you'll need to create a Personal Access Token (PAT) that has full access to the repos scope for your account. The actions in this repository are already configured to use my PAT, it's setup as a secret on this repo, named `PAT`. If you fork the repository to try these examples out for yourself, you'll need to setup a PAT of your own so the actions trigger correctly.
