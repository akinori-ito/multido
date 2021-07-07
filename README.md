# multido

Execute command at multiple hosts automatically using ssh

This is an expect (tcl) script to execute a command in multiple hosts.
It assumes that you have accounts in the hosts with the same user name
and password. Then multido logs in the host one-by-one using the same
username and password, and then executes the command.

## Usage

```
Usage: multido [-sudo] hostfile command [ssh_options]
  hostfile: a file that contains the list of hostnames
            if hostfiles begins with =, the rest is regarded
            as a single hostname.
  command: command to be executed
  ssh_options: options to be used to the ssh command
  -sudo:    execute the command as a superuser at the remote
            host using sudo command
```

## Example

Suppose the file "hosts" contains the following lines:
```
user@foo.example.com
user@bar.example.com
user@baz.example.com
```
then the command
```
   multido hosts ls
```
executes "ls" command in the listed hosts. Upon execution, it asks the password.
