## jupyter-installer.yml
This playbook downloads and installs Anaconda3, installs R and enables IRKernel for Jupyter on CentOS 7. Run the playbook as,
```bash
ansible-playbook jupyter-installer.yml -i inventory/
```

To start Jupyter, run
```bash
source <home_dir>/anaconda/bin/activate
jupyter notebook --allow-root --no-browser --port=5000 --ip=0.0.0.0
```
Jupyter will start on port 5000 on the node and output something like below.

```
To access the notebook, open this file in a browser:
file:///home/purba/.local/share/jupyter/runtime/nbserver-121189-open.html
Or copy and paste one of these URLs:
http://Testing:5000/?token=<redacted_token>
or http://127.0.0.1:5000/?token=<redacted_token>
```

Go to the browser and type `http://<node_ip>:5000`. This will ask you for a token. Copy the token displayed like above and paste it in the input box.

To stop jupyter, simply press `Control+C`. To deactivate anaconda environment, enter `conda deactivate`.