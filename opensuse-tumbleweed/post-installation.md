# Git

```bash
sudo zypper in git
```

- When using git for the first time, don't use it from terminal.
- Use vscode built-in terminal to push something on github because vscode has integration to sign in to github and you will be saved from using ssh and other cred management issues.

# Oh-my-bash

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)"

# Change theme to "robbyrussell" in .bashrc
```

# Vscode
- Adding repository of vscode.

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/vscode.repo'
```

- Refreshing the local repos and installing code.

```bash
sudo zypper refresh
sudo zypper install code
```