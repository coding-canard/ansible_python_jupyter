## python3-installer.yml
This playbook downloads, compiles and installs Python 3.7.0 from source on CentOS 7 and creates a virtual environment. Since CentOS 7 comes packaged with python 2.7.x, the playbook makes and alternate installation of python3. Run the playbook as,
```bash
ansible-playbook python3-installer.yml -e '{"venv": "virtual_env"}'
```

This will create a virtual environment named virtual_env. If the argument is not passed, it will by default create a virtual environment named virtual_py. Additionally, to install packages in the virtual environment, run
```bash
ansible-playbook python3-installer.yml -e '{"venv": "virtual_env", "pkgs": ["numpy", "pandas", "seaborn"]}'
```

