# How to deploy keen.js

## Preparing the release

1. Create a new `CHANGELOG.md` entry with information about this release ([example](https://github.com/keen/keen-js/blob/431c24b44047adec449184fba0b6a22ca9fdb129/CHANGELOG.md)).
2. Update `README.md` `docs/README.md`, and `docs/installation.md` files to reflect what the new CDN URLs and library versions _will_ be once this release is live.

## Cutting the release

* Create a new tag: `npm version patch` [NPM SEMVER](https://docs.npmjs.com/cli/version)

## Verify the release

* [Check the repo releases](https://github.com/keen/keen-js/releases) and download the ZIP file to ensure that the `dist` folder and built files are there. If so, continue...

## Deploying to NPM

**Beware: this is a one-time deal. Releases cannot be re-published!**

* Deploy this tag the npm: `npm publish`

## Deploying to AWS:

Run this command with the appropriate AWS and aws_secret keys:

```ssh
$ export AWS_KEY={AWS KEY}
$ export AWS_SECRET={AWS SECRET}
$ gulp deploy
```

This will test, build, and deploy the files to AWS.

This [blog post](https://viget.com/extend/publishing-packages-to-npm-and-bower) was especially helpful with information on
publishing to `npm` and `bower`.
