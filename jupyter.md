
# Working with Jupyer notebooks 

1. Use `jupytext` to [convert the notebook](https://github.com/mwouts/jupytext#command-line-conversion) to a plain text python file
 
```
# Turn notebook.ipynb into a paired ipynb/py notebook
jupytext --set-formats ipynb,py notebook.ipynb

# Update all paired representations of notebook.ipynb  
jupytext --sync notebook.ipynb                  
```
 
2. Open `.py` file in VSCodium
 
## Links

https://stackoverflow.com/a/56753936/3362993

https://code.visualstudio.com/docs/python/jupyter-support#_debug-a-jupyter-notebook
