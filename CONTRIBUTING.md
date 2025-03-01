delete
end
























































































## Submitting the Pull Request

- Create a new branch locally.
- Make your changes in that branch to your fork repository
- Submit a pull request from your topic branch to the main branch on the `octokit/plugin-paginate-graphql.js` repository.
- Be sure to tag any issues your pull request is taking care of / contributing to. Adding "Closes #123" to a pull request description will automatically close the issue once the pull request is merged in.

## Testing a pull request from github repo locally:

You can install `@octokit/plugin-paginate-graphql` from each pull request. Replace `[PULL REQUEST NUMBER]`

Once you are done testing, you can revert back to the default module `@octokit/plugin-paginate-graphql` from npm with `npm install @octokit/plugin-paginate-graphql`

## Merging the Pull Request & releasing a new version

Releases are automated using [semantic-release](https://github.com/semantic-release/semantic-release).
The following commit message conventions determine which version is released:

1. `fix: ...` or `fix(scope name): ...` prefix in subject: bumps fix version, e.g. `1.2.3` → `1.2.4`
2. `feat: ...` or `feat(scope name): ...` prefix in subject: bumps feature version, e.g. `1.2.3` → `1.3.0`
3. `BREAKING CHANGE:` in body: bumps breaking version, e.g. `1.2.3` → `2.0.0`

Only one version number is bumped at a time, the highest version change trumps the others.
Besides publishing a new version to npm, semantic-release also creates a git tag and release
on GitHub, generates changelogs from the commit messages and puts them into the release notes.

Before the publish it runs the `npm run build` script which creates a `pkg/` folder with distributions for browsers, node and TypeScript definitions. The contents of the `pkg/` folder are published to the npm registry.

If the pull request looks good but does not follow the commit conventions, use the <kbd>Squash & merge</kbd> button.
