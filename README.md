# DevEnvironments

# Virtual Machines
For when virtual machines are needed, one can setup a base a virtual machine with git access by running
the following commands from a shell:
```
multipass launch 25.10 --name minivm-01 --memory 4G --disk 40G --cloud-init cloud-init.yaml
cd ~
multipass transfer .ssh/id_rsa minivm-01:./.ssh/id_rsa
multipass transfer .ssh/id_rsa.pub minivm-01:./.ssh/id_rsa.pub
```
From there one can clone additional VM's with the command
```
multipass clone minivm-01 --name [some-name]
```

