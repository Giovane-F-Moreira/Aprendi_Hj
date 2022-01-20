# ReactJS

O ReactJS é um framework em JS para desenvolvimento, ele utiliza a componentização para criar seus layout e estrutura interna.
Primeiro, antes de tudo, precisamos intalar o NVM e o NODE 

NVM = ('Gerenciadores de versão de **Node**') 
NODE = ('O **Node.js** se caracteriza como um ambiente de execução JavaScript')

Vamos lá, iremos seguir o tutorial retirado da pagina de instalação oficial do Node:

### Install & Update Script

If you don't have curl installed, install it with:

```
sudo apt install curl
```

To **install** or **update** nvm, you should run the [install script](https://github.com/nvm-sh/nvm/blob/v0.39.1/install.sh). To do that, you may either download and run the script manually, or use the following cURL or Wget command:

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

Running either of the above commands downloads a script and runs it. The script clones the nvm repository to `~/.nvm`, and attempts to add the source lines from the snippet below to the correct profile file (`~/.bash_profile`, `~/.zshrc`, `~/.profile`, or `~/.bashrc`).

```
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

Run, to install the LTS version

```
nvm install --lts
```

Now, check the installed version

```
npm -v
node -v
```

Check the official repository for possible updates:

```
https://github.com/nvm-sh/nvm
```