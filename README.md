# __ansible__
This repo contains experiments using Ansible. Please use the playbook at your own risk.

This ReadMe will be updated when the playbooks are updated or more added.

## python3-installer.yml
This playbook downloads, compiles and installs Python 3.7.0 from source on CentOS 7 and creates a virtual environment. Since CentOS 7 comes packaged with python 2.7.x, the playbook makes and alternate installation of python3. Run the playbook as,
```bash
ansible-playbook python3-installer.yml -i inventory/ -e '{"venv": "virtual_env"}'
```

This will create a virtual environment named virtual_env. If the argument is not passed, it will by default create a virtual environment named virtual_py. Additionally, to install packages in the virtual environment, run
```bash
ansible-playbook python3-installer.yml -i inventory/ -e '{"venv": "virtual_env", "pkgs": ["numpy", "pandas", "seaborn"]}'
```
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
