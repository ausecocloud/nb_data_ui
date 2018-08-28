# nb_data_ui

A very simple Jupyter Notebook extension to access DropBox from the Notebook UI.

## Test and development

```bash
# start a container
docker run --rm -it -p 8888:8888 -v $(PWD):/nb_data_ui jupyter/base-notebook:latest bash
# install pkg and enable jupyter extension
pip install -e /nb_data_ui
jupyter serverextension enable --py nb_data_ui
jupyter nbextension install --user --py -s nb_data_ui
jupyter nbextension enable nb_data_ui --user --py
# setup drobpox api key
echo '{"dropbox": {"appkey": "<your api key>"}}' > ~/.jupyter/nbconfig/fetch.json
# start notebook
start-notebook.sh
```

The last start command should print out a url to access the notebook server
This should look something like this:

  http://localhost:8888?token=<printed token>
  
