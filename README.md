# tools
Miscellaneous python tools


### Install
```bash
git clone https://github.com/clatworthylab/kttools.git
echo 'export PYTHONPATH=/path/to/kttools:$PYTHONPATH' >> ~/.bash_profile # or ~/.bashrc
source ~/.bash_profile # or ~/.bashrc

# or 
pip install git+https://github.com/clatworthylab/kttools.git
```

### Usage
```python
import tools
```


### jupyterhub issue

On jupyterhub, If you find yourself trying to import from local directory, i.e. `git clone`, and finding that you can't import it, you will need to edit your your `kernel.json` file like so:

```bash
vi /home/jovyan/.local/share/jupyter/kernels/<condaenvironmentname>/kernel.json 
```

add in the `$PATH` and `$PYTHONPATH` bits:
```bash
{
 "argv": [
  "/home/jovyan/my-conda-envs/<condaenvironmentname>/bin/python",
  "-m",
  "ipykernel_launcher",
  "-f",
  "{connection_file}"
 ],
 "env": {
     "PATH": "/home/jovyan/scripts/kttools:$PATH",
     "PYTHONPATH": "/home/jovyan/scripts/kttools:$PYTHONPATH"
 },
 "display_name": "Python (<condaenvironmentname>)",
 "language": "python"
}
```
