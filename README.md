# common-swift-package

This repository holds files which are shared between my swift packages. They are automatically synced using [this](https://github.com/BetaHuhn/repo-file-sync-action) GitHub Action:

[![Sync Files](https://github.com/Nef10/common-swift-package/actions/workflows/sync.yml/badge.svg)](https://github.com/Nef10/common-swift-package/actions/workflows/sync.yml)

## Contents

* GitHub Actions:
  * CI with minimum code coverage check
  * Code Coverage comment on PRs
  * Documentation build with jazzy and push to GitHub pages on tag
  * [Label Syncer](https://github.com/micnncim/action-label-syncer) to syncronize GitHub issue and PR labels
  * [Release Drafter](https://github.com/release-drafter/release-drafter) to automatically draft release notes based on merged PRs
  * [swift-dependency-updater](https://github.com/Nef10/swift-dependency-updater) running as a cron job
  * Dependabot configuration to update GitHub actions
* `.swiftlint.yml` with my [default config](https://github.com/Nef10/swiftlint-config)
* `.gitignore`
* `LICENSE`

## Configuration

To allow these files to serve all packages there are some configuration options:

* Place a `minimum_coverage.txt` file containing a single number in the `.github` folder to enforce a minimum code coverage percentage in the CI workflow
* Place an empty `macos_only` file in the `.github` folder to disable testing the package on ubuntu, for example when using mac only frameworks
* Place a `macos_version.txt` file containing a valid [GitHub Actions Virtual Environments label](https://github.com/actions/virtual-environments/tree/main) in the `.github` folder to run the macOS tests on a version other than `macOS-latest`
