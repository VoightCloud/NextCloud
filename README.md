# NextCloud
This installs the NextCloud server.

### Usage
#### Installation:
```shell script
cd ansible
ansible-playbook --vault-password-file=~/password.txt playbook.yaml
```

#### Removal
```shell script
cd ansible
ansible-playbook --vault-password-file=~/password.txt reset.yaml
```

#### A Note about Ansible Vault
We use Ansible Vault to encrypt our credentials.
If you don't have the password file, you won't be able to decrypt the vault.
However, you are more than welcome to create your own credentials.
Simply look in the files/vault.yaml file and create your own credentials as follows:
```shell script
echo 'YourV3ry5trongP@$$w0rd' > ~/password.txt
chmod 0600 ~/password.txt
ansible-vault encrypt_string --vault-password-file=~/password.txt "StringToEncrypt" --name="NameOfCredential"
```
When you're happy with the results, copy the text into the vault.

