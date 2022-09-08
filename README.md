# amazon-linux-2-jupyterlab-server
Short guide to running a jupyterlab server immediately with the amazon-linux-2 ec2 image

1. Install python3.8 on your ec2 server
```
sudo amazon-linux-extras install python3.8
python3.8 -m pip install --user virtualenv
python3.8 -m virtualenv -p python3.8 venv
source venv/bin/activate
pip install jupyterlab
deactivate
```

2. Configure your server password
```
jupyter server --generate-config
jupyter server password # Enter and verify your password here
nano .jupyter/jupyter_server_config.py'
c.JupyterApp.config_file_name = 'jupyter_notebook_config.json'
```

3. Run your JupyterLab server!
```
screen -dm bash -c './start_jupyterlab.sh'
```
