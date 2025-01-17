<head>
  <meta charset="UTF-8">
  <meta name="description" content="Contributing to ROCm">
  <meta name="keywords" content="ROCm, contributing, contribute, maintainer, contributor">
</head>

# Contribute to ROCm documentation

All ROCm projects are GitHub-based, so if you want to contribute, you can do so by:

* [Submitting a pull request in the appropriate GitHub repository](#submit-a-pull-request)
* [Creating an issue in the appropriate GitHub repository](#create-an-issue)
* [Suggesting a new feature](#suggest-a-new-feature)

```{important}
By creating a pull request (PR), you agree to allow your contribution to be licensed under the terms of the
LICENSE.txt file in the corresponding repository. Different repositories may use different licenses.
```

## Submit a pull request

To make edits to our documentation via PR, follow these steps:

1. Identify the repository and the file you want to update. For example, to update this page, you would
  need to modify content located in this file:
  `https://github.com/ROCm/ROCm/blob/develop/docs/contribute/contributing.md`

2. (optional, but recommended) Fork the repository.

3. Clone the repository locally and (optionally) add your fork. Select the green 'Code' button and copy
   the URL (e.g., `git@github.com:ROCm/ROCm.git`).

   * From your terminal, run:

      ```bash
      git clone git@github.com:ROCm/ROCm.git
      ```

   * Add your fork to this local copy of the repository. Run:

      ```bash
      git add remote <name-of-my-fork> <git@github.com:my-username/ROCm.git>
      ```

      To get the URL of your fork, go to your GitHub profile, select the fork and click the green 'Code'
      button (the same process you followed to get the main GitHub repository URL).

4. Check out the **develop** branch and run 'git pull' (and/or 'git pull origin develop' to ensure your
  local version has the most recent content.

5. Create a new branch.

    ```bash
    git checkout -b my-new-branch
    ```

6. Make your changes locally using your preferred code editor. If you're editing documentation, follow
  the guidelines listed on the
  [documentation structure](./doc-structure.md) page.

7. (optional) We recommend running a local test build to ensure the content looks the way you expect.

    In your terminal, run:

    ```bash
    python3 -mvenv .venv

    .venv/Scripts/python -m pip install -r docs/sphinx/requirements.txt
    .venv/Scripts/python -m sphinx -T -E -b html -d _build/doctrees -D language=en docs _build/html
    ```

    The build files are located in the `docs/_build` folder. To preview your build, open the index file
    (`docs/_build/html/index.html`) file. For more information, see
    [Building documentation](building.md). To learn
    more about our build tools, see
    [Documentation toolchain](toolchain.md).

8. Commit your changes and push them to GitHub. Run:

    ```bash
    git add <path-to-my-modified-file> # to add all modified files, you can use: git add .

    git commit -m "my-updates"

    git push <name-of-my-fork>
    ```

    After pushing, you will get a GitHub link in the terminal output. Copy this link and paste it into a
    browser to create your PR.

## Create an issue

1. To create a new GitHub issue, select the 'Issues' tab in the appropriate repository
  (e.g., https://github.com/ROCm/ROCm/issues).
2. Use the search bar to make sure the issue doesn't already exist.
3. If your issue is not already listed, select the green 'New issue' button to the right of the page. Select
  the type of issue and fill in the resulting template.

### General issue guidelines

* Use your best judgement for issue creation. If your issue is already listed, upvote the issue and
  comment or post to provide additional details, such as how you reproduced this issue.
* If you're not sure if your issue is the same, err on the side of caution and file your issue.
  You can add a comment to include the issue number (and link) for the similar issue. If we evaluate
  your issue as being the same as the existing issue, we'll close the duplicate.
* If your issue doesn't exist, use the issue template to file a new issue.
  * When filing an issue, be sure to provide as much information as possible, including script output so
    we can collect information about your configuration. This helps reduce the time required to
    reproduce your issue.
  * Check your issue regularly, as we may require additional information to successfully reproduce the
    issue.

## Suggest a new feature

Use the [GitHub Discussion forum](https://github.com/ROCm/ROCm/discussions)
(Ideas category) to propose new features. Our maintainers are happy to provide direction and
feedback on feature development.

## Future development workflow

The current ROCm development workflow is GitHub-based. If, in the future, we change this platform,
the tools and links may change. In this instance, we will update contribution guidelines accordingly.
