# To create a release

The releases are automated via GitHub actions, using [this configuration file](https://github.com/garmir/spotify-cli/blob/master/.github/workflows/cd.yml).

The release is triggered by pushing a tag.

1. Bump the version in `Cargo.toml` and run the app to update the `lock` file
1. Update the "Unreleased" header for the new version in the `CHANGELOG`. Use `### Added/Fixed/Changed` headers as appropriate
1. Commit the changes and push them.
1. Create a new tag e.g. `git tag -a v0.7.0` and add the CHANGELOG to the commit body
1. Push the tag `git push --tags`
1. Wait for the build to finish on the [Actions page](https://github.com/garmir/spotify-cli/actions)
1. This should publish to cargo as well

### Update `brew`

1. `cd` to the [`tap` repo](https://github.com/garmir/homebrew-tap)
1. Run script to update the Formula `sh scripts/spotify-cli.sh $VERSION`

### Update `scoop` (Windows 10)

1. `cd` to [the `scoop` repo](https://github.com/garmir/scoop-bucket)
1. Run the script to update the manifest `sh scripts/spotify-cli.sh $VERSION`
