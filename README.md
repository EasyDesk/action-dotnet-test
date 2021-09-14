# action-dotnet-test

An action that can be used to run a .NET test project.

## Usage
By default, this action requires the build to be up to date for the given `build-configuration`.
To that purpose, you can use [EasyDesk/action-dotnet-build](https://github.com/EasyDesk/action-dotnet-build).
Otherwise, you can force a new build with `skip-build: false`.

### Usage example
```yaml
    steps:
      - uses: EasyDesk/action-dotnet-test@v1
        with:
          # (Optional) The root where the 'dotnet test' command should look for a project or a solution.
          # If not specified, defaults to the current directory.
          path: '<path-to-test-project>'

          # (Optional) Additional command line arguments to be passed to 'dotnet test'.
          # Emtpy by default.
          test-args: '<additional-test-args>'

          # (Optional) The build configuration.
          # If not specified, defaults to 'Release'.
          build-configuration: Release

          # (Optional) Whether to skip the build using the '--no-build' flag.
          # If not specified, defaults to true.
          skip-build: true
```