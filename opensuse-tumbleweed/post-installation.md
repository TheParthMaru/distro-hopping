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

# MySQL

- Download the mysql repository rpm package file from the link: https://dev.mysql.com/downloads/repo/suse/
- This will be mysql-8.0 version.

```bash
sudo rpm -Uvh package-name.rpm

# Example
sudo rpm -Uvh mysql80-community-release-sl15-8.noarch.rpm
```

- Where `-Uvh` stands for upgrade, verbose and hash.
- Import MySQL GnuPG Key

```bash
sudo rpm --import /etc/RPM-GPG-KEY-mysql
```

- Install mysql community server

```
sudo zypper install mysql-community-server
```

- Start server
```
systemctl start mysql
```

- Check server status
```
systemctl status mysql
```

- Initially a temporary password is generated for user `root`.
```
sudo grep 'temporary password' /var/log/mysql/mysqld.log
```

- Change the root password
```
mysql -uroot -p <temporary_password>

mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'Parth@26898';
```

# Nodejs with NVM
- Link: https://github.com/nvm-sh/nvm?tab=readme-ov-file#installing-and-updating

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# You can close and open your terminal and by default the below path will be exported. If not then add the below path in .bashrc
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm

# Reload configurations
source .bashrc

# Check version
nvm -v

# Install the latest nodejs
nvm install latest
```