# GitHub Billing Report

[![GitHub Super-Linter](https://github.com/aatmmr/github-billing-report/actions/workflows/linter.yml/badge.svg)](https://github.com/super-linter/super-linter)
![CI](https://github.com/aatmmr/github-billing-report/actions/workflows/ci.yml/badge.svg)

## Development

After you have cloned the repository to your local machine or codespace, you will
need to perform some initial setup steps before you can develop the action.

> [!NOTE]
>
> You'll need to have a reasonably modern version of
> [Node.js](https://nodejs.org) handy. If you are using a version manager like
> [`nodenv`](https://github.com/nodenv/nodenv) or
> [`nvm`](https://github.com/nvm-sh/nvm), you can run `nodenv install` in the
> root of your repository to install the version specified in
> [`package.json`](./package.json). Otherwise, 16.x or later should work!

1. :hammer_and_wrench: Install the dependencies

   ```bash
   npm install
   ```

1. :building_construction: Package the TypeScript for distribution

   ```bash
   npm run bundle
   ```

1. :white_check_mark: Run the tests

   ```bash
   $ npm test

   PASS  ./index.test.js
     ✓ throws invalid number (3ms)
     ✓ wait 500 ms (504ms)
     ✓ test runs (95ms)

   ...
   ```

1. Format, test, and build the action

   ```bash
   npm run all
   ```

   > [!WARNING]
   >
   > This step is important! It will run [`ncc`](https://github.com/vercel/ncc)
   > to build the final JavaScript action code with all dependencies included.
   > If you do not run this step, your action will not work correctly when it is
   > used in a workflow. This step also includes the `--license` option for
   > `ncc`, which will create a license file for all of the production node
   > modules used in your project.

### Testing Action Locally

In order to test the action locally [act](https://github.com/nektos/act) can be used. Please follow the [installation instructions](https://github.com/nektos/act#installation) to install `act` on your machine. The repository holds a [test workflow](./.github/workflows/test-action.yml) that can be used to test the action locally. To run this workflow with `act`, run the following command:

```bash
act -W .github/workflows/test-action.yml
```

from the root of the repository.