# Cutting a new release of wasi-hyperium

To cut a new release, you will need to do the following:

1. Confirm that [CI is green](https://github.com/fermyon/wasi-hyperium/actions) for the commit selected to be tagged and released.

2. Change the workspace version number in [Cargo.toml](./Cargo.toml).

3. Create a pull request with these changes and merge once approved.

4. Checkout the commit with the version bump from above.

5. Create and push a new tag with a `v` and then the version number.

    As an example, via the `git` CLI:

    ```
    # Create a GPG-signed and annotated tag
    git tag -s -m "wasi-hyperium v0.3.0" v0.3.0

    # Push the tag to the remote corresponding to fermyon/wasi-hyperium (here 'origin')
    git push origin v3.1.0
    ```

6. Pushing the tag upstream will trigger the [release action](https://github.com/fermyon/wasi-hyperium/actions/workflows/release.yml) which publishes the crates in this workspace to `crates.io`.