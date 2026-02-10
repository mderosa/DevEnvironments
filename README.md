# DevEnvironments

# Virtual Machines
multipass launch 25.10 --name minivm-01 --memory 4G --disk 40G --cloud-init cloud-init.yaml
multipass transfer ~/.ssh/id_rsa minivm-01:./.ssh/id_rsa
multipass transfer ~/.ssh/id_rsa.pub minivi-01:./.ssh/id_rsa.pub