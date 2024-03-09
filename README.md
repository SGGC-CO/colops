## Run the example playbook

1. Run the following command to start mongodb cluster locally.

```bash
make mongoc
```

## Connection Type

1. local: The role uses to do some action on the local machine.
2. ssh: The role uses to do some action on the remote machine.

## Inventory

`gol_server` is an aliases of the server for initial setup use in the inventory file.

### Variables

1. domain: domain name of the server

### Groups

```yaml
[localhost] ## for local machine

[gol_server] ## for remote machine
```

## Credentials

create a file `credentials_[development/production].yml`. use the following command to create the file.

```bash
ansible-vault create credentials_[development/production].yml
```

create a text file `passwordfile` use for open credentials file by `--vault-password-file ./path/to/file`. use the following command to create the file.

```bash
echo "password" > passwordfile
```

**_ dont forget to put passwordfile in gitignore _**

## Naming Rules

1. All the roles should be named in lowercase and should be hyphen separated start with `ansible-role`.
2. The role name should not contain any special characters or spaces.
3. The role's variables should be under-line separated and should be in lowercase.(e.g. some_name, `defaults/main.yml`)
4. The role scope variables should be in uppercase and should be under-line separated.(e.g. RSA_NEW, `ansible-role-lsk/tasks/main.yml`)
