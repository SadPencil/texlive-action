# texlive-action

This is a fork from [xu-cheng/texlive-action](https://github.com/xu-cheng/texlive-action).

GitHub Action to run arbitrary commands in a [TeXLive](https://www.tug.org/texlive/) environment.

It comes with one flavor, `full`. The `full` action has all TeXLive packages installed.
The base image is debian.
See the [dockerfile](https://hub.docker.com/r/svlentink/texlive-full/dockerfile) for the scripts to build the respective docker images.

This action is suitable to run arbitrary commands in a LaTeX environment.

## Inputs

* `run`: Arbitrary bash codes to be executed.

## Example

* Run commands in a **full** TeXLive environment.

  ```yaml
  on: [push]
  jobs:
    build_latex:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v2
        - uses: SadPencil/texlive-action/full@v2
          with:
            run: |
              apt-get update
              apt-get install make
              make
  ```

## License

MIT
