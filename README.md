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
