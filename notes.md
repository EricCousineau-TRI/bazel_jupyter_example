coarse debugging notes

## app dir
```sh
$ python -m venv .
$ source bin/activate
$ pip install 'jupyterlab<=3.5'
$ pip show -f jupyterlab | grep 'bin/'
  ../../../bin/jlpm
  ../../../bin/jupyter-lab
  ../../../bin/jupyter-labextension
  ../../../bin/jupyter-labhub
$ jupyter lab paths
Application directory:   /home/eacousineau/tmp/jupyter-venv-pure/share/jupyter/lab
User Settings directory: /home/eacousineau/tmp/jupyter-venv-pure/etc/jupyter/lab/user-settings
Workspaces directory: /home/eacousineau/tmp/jupyter-venv-pure/etc/jupyter/lab/workspaces
```

need deps;
```
file $(bazel info output_base)/external/external/pip_deps_jupyterlab/data/share/jupyter/lab/static/index.html
```
can also access via
```
./bazel-bin/tools/jupyter/example.runfiles/pip_deps_jupyterlab/site-packages/jupyterlab/static
```

note sure which one is best

^^^ `/static` is under `Application directory` above

## ipywidgets

widgets do not work... probably some weird need to install / overwrite `jupyterlab` share

in above pure virtualenv + pip

```sh
$ pip show -f jupyterlab-widgets
...
Required-by: ipywidgets
Files:
  ../../../share/jupyter/labextensions/@jupyter-widgets/jupyterlab-manager/install.json
  ../../../share/jupyter/labextensions/@jupyter-widgets/jupyterlab-manager/package.json
  ../../../share/jupyter/labextensions/@jupyter-widgets/jupyterlab-manager/schemas/@jupyter-widgets/jupyterlab-manager/package.json.orig
...
  ../../../share/jupyter/labextensions/@jupyter-widgets/jupyterlab-manager/static/remoteEntry.9f387e5e108e458f62c3.js
  ../../../share/jupyter/labextensions/@jupyter-widgets/jupyterlab-manager/static/style.js
  ../../../share/jupyter/labextensions/@jupyter-widgets/jupyterlab-manager/static/third-party-licenses.json
...
```
