# Install WSL (Windows Subsystem for Linux Installed) #
  1. Open Microsoft Store on your machine and search for Ubuntu 20.04 (Linux distro) and install it.
  2. After the installation is complete, the shell should open up automatically to complete the installation.
  3. OR type in Ubuntu in the App and open it. 
  4. It will ask for username and password which need not be the same as your windows. Whenever asked for password going forward, give this password.

# Install zsh #
  1. First update the package list. 
    a. `sudo apt update` - to check if updates are available.
    b. If yes, update using
      `sudo apt-get update` or `sudo apt upgrade``
  2. Install zsh
    a. `sudo apt install zsh`
    b. When asked for type one of the keys in parentheses - type '2'
    
 # Install ohmyzsh #
  1. Visit site ohmyz.sh and go to Install oh-my-zsh
  2. Install via curl or wget. Paste the command in ubuntu shell. Pasting the same command below:
    `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
  3. When asked for changing the default shell to zsh. Type ‘y’

# How to open and edit zshrc file. You can use any text editor #
  1. `vi  ~/.zshrc`
  2. `i` - switch to insert mode
  3. `Esc` - switch to command mode
  4. `:wq` - save and quit

# Install Homebrew #
  1. Paste below commands in Ubuntu shell:
    a. `sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"`
    b. `test -d ~/.linuxbrew && eval $(~/.linuxbrew/bin/brew shellenv)`
    c. `test -r ~/.bash_profile && echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.bash_profile`
    d. `echo "eval \$($(brew --prefix)/bin/brew shellenv)" >>~/.profile`
  2. Verify installation
    a. `brew doctor`
    b. `brew list`
  Note: `brew <command> --cask` will not work as it is specific to Mac. There are other options for windows out there but I was comfortable
  downloading.
  
# Install zsh-syntax-highlighting #
  1. `brew install zsh-syntax-highlighting`
  2. `vi  ~/.zshrc`
  3. Add to zshrc file: 
    `source /home/linuxbrew/.linuxbrew/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh`
  4. `source ~/.zshrc`

# Install zsh-autosuggestions #
  1. `brew install zsh-autosuggestions`
  2. `vi  ~/.zshrc`
  3. Add to zshrc file:
    `source /home/linuxbrew/.linuxbrew/share/zsh-autosuggestions/zsh-autosuggestions.zsh`
  4. `source ~/.zshrc`

# Install VScode #
  1. Download [Visual Studio Code](https://code.visualstudio.com/download) (Windows version and not the Ubuntu version)
  2. First time there will not be Ubuntu bash in VS code. So in windows bash, type ‘code .’ This will set up the communication between VSCode and WSL
  3. A new VSCode window will pop up and if it asks if you ‘trust the authors’, hit yes.

# SSH keys #
  1. First create pbcopy using [link](https://www.techtronic.us/pbcopy-pbpaste-for-wsl/)
  2. Now follow the steps as in tools set up for Mac.

# Create nf_base environment #
  (Note: you can copy the existing environment i.e environment.yml also check [link](https://github.com/neuefische/da-getting-started/blob/main/2_Virtual_environments_Anaconda_Miniconda.md))
  1. `conda create –name nf_base python=3.10`
  2. `conda activate nf_base`
  3. `conda install pip matplotlib numpy pandas scipy seaborn statsmodels scikit-learn nb_conda`
  4. `conda deactivate`

# Create nf_geo environment (in terminal from VS Code) #
  1. `conda create -n nf_geo -c conda-forge geopandas`

# Create nf_sql environment #
  1. `conda create --clone nf_base --name nf_sql`
  2. `conda activate nf_sql`
  3. `conda install -n nf_sql -c conda-forge python-dotenv`
  4. `conda install -n nf_sql sqlalchemy`
  5. `conda install -n nf_sql -c conda-forge psycopg2`

# Create nf_cluster environment #
  1. `conda create –clone nf_base –name nf_cluster`
  2. `conda install python-dotenv`

# DBeaver CE #
  1. Go to [link](https://dbeaver.io/download/)
  2. Click under Windows section ‘Install from Microsoft Store’

# Tableau #
  1. Install from the [link](https://help.tableau.com/current/desktopdeploy/en-us/desktop_deploy_download_and_install.htm)
  2. While trying to connect to Postgres, it will promp to download the drivers. Download it.
  3. **Close the Tableau and Reopen**
  4. Now it will connect to Postgres.

# References #
https://www.how2shout.com/how-to/how-to-install-homebrew-on-linux-or-wsl.html
https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode
https://www.youtube.com/watch?v=xlgyZ1_OlsY
https://dev.to/contactsunny/installing-zsh-and-oh-my-zsh-on-windows-11-with-wsl2-1p5i
https://www.redhat.com/sysadmin/introduction-vi-editor
https://github.com/neuefische/da-getting-started/blob/main/2_Virtual_environments_Anaconda_Miniconda.md
https://www.techtronic.us/pbcopy-pbpaste-for-wsl/

