# Installation steps

1. Install homebrew manually:

    This is due to https://github.com/geerlingguy/ansible-role-homebrew/issues/18 
    ```
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    ```

2. Run automated installer:

    Set `--roles-path` explicitly because of https://github.com/ansible/ansible/issues/16010 
    ```
    ansible-galaxy install -r requirements.yml --roles-path=roles
    ansible-playbook main.yml -u scottrigby -U scottrigby --ask-sudo-pass
    ```

3. For updates, you must run:

    Use the chown command on updates also because of https://github.com/geerlingguy/ansible-role-homebrew/issues/18
    ```
    sudo chown -R $(whoami):admin /usr/local
    ansible-playbook main.yml -u scottrigby -U scottrigby --ask-sudo-pass
    ```

4. Install dotfiles separately with homeshick.
