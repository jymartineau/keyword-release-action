# Keyword Releaser 2700

made with :purple_heart: by <img src="https://github.com/jymartineau.png" width="50" height="50" alt="GitHub Avatar">

# GitHub Action to Create Releases Based on a Keyword
The Keyword Releaser will create a release based on the keyword specified in the arguments.

# Environment Variables
- `GITHUB_TOKEN` - _Required_ Allows the Action to authenticte with the GitHub API to create the release.

# Arguments
- _Required_ - A single keyword.  If the keyword is found in a commit message, a release will be created.  Although case is ignored, it's suggested to use a unique, uppercase string like `FIXED`, `READY_TO_RELEASE`, or maybe even `PINEAPPLE`.

# Examples
Here's an example workflow that uses the Keyword Releaser action.  The workflow is triggered by a `PUSH` event and looks for the keyword `"FIXED"`.

```
name: keyword-releaser

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
    - uses: actions/checkout@v3
    - uses: jymartineau/keyword-release-action@master
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      with:
        args: 'FIXED'
```

# keyword-release-action
