# mlops-zoomcap
Repo for the mlops course from DataTalksClub


## Initialization

### Docker and docker-compose
Install the necessary tools
`sudo apt install docker.io`

Create a directory and download docker-compose there. You can find docker-compose at https://github.com/docker/compose : 
```bash
mkdir soft # folder where to save software exec
cd soft 
wget <docker-compose release> -O docker-compose 
chmod +x docker-compose
```

Make docker compose executable from anywhere: `echo 'export PATH="${HOME}/soft:${PATH}"' >> .zshrc` 

Grant yourself root permission to run docker (more here https://docs.docker.com/engine/install/linux-postinstall/):
```bash
sudo groupadd docker
sudo usermod -aG docker $USER
```
Log out and Log back in

### Pyenv and poetry
Install pyenv:
```bash
curl https://pyenv.run | bash

echo '
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv init --path)"
eval "$(pyenv virtualenv-init -)"
' >> ~/.zshrc

exec "$SHELL"

pyenv install <your python version>
```

Install poetry
```bash
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -source $HOME/.poetry/env

mkdir mlops # create project folder or donwload repo
cd mlops 
pyenv local <your python version>
poetry new <project name>
cd <project name>
poetry install
poetry shell
poetry add --dev black flake8
```


### jupyter and port forwarding 
If you are on a remote machine you might want to install jupyter notebook and run it on your remote while using it on your local machine. 

Check last 3 mins of [this video](https://www.youtube.com/watch?v=IXSiYkP23zo&list=PL3MmuxUbc_hIUISrluw_A7wDSmfOhErJK)
