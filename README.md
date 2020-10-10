# xcode-select

This GitHub Action is a wrapper around `xcode-select` and will let you easily pick a specific Xcode version to be used in your workflow.

## Usage

The most basic usage will be without any inputs, which will default to `version: "latest"`, which will result in the latest stable Xcode being selected.

```yml
steps:
  - uses: devbotsxyz/xcode-select@v1
```

If you want to pin a specific version, specify it with the `version` input.

```yml
steps:
  - name: "Select Xcode 11.7"
    uses: devbotsxyz/xcode-select@v1
      with:
        version: "11.7"
```

If you are less specific with the version, this Action will pick the latest available release for that version. For example, now in October 2020, specifying `12` will give you `12.0.1` and specifying `11` will get you `11.7`

### Xcode Beta

You can set the `beta` input to `true` to request a beta release. For example to get the latest Beta in the Xcode 12 release, use the following:

```yml
steps:
  - uses: devbotsxyz/xcode-select@v1
    with:
      version: "12"
      beta: "true"
```

To get the latest available beta, which may not always exist, use the following:

```yml
steps:
  - uses: devbotsxyz/xcode-select@v1
    with:
      version: "latest"
      beta: "true"
```

## License

This action is released under the [MIT License](LICENSE).

## Contributions

Contributions are welcome. One of the most impactful things you can do is to file issues for bugs and use-cases that were not throught of yet.
