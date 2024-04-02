# Bazel-Jupyter Stuff

Example of using JupyterLab with Bazel's `rules_python`.

## Setup

Ensure you have Bazelisk installed. Then you can do:

```sh
bazel run //tools/jupyter:example
```

See [tools/jupyter README](./tools/jupyter/README.md) for more details on
usage and examples.

## Known Issues

- Dunno how to make `jupyterlab-widgets` actually install correctly. See coarse
  notes in `/notes.md`. When you run `example` above, `ipywidgets` will import, but
  it won't render correctly.
