I. Summary

Brief descriptions about ansible architecture, they follow the client-server model, inside them as:
+ Server: called Control Machine
+ Client: called Remote Machine

As opposed to puppet, Ansible use the agentless model with client, It's meaning, you don't have to install anything in client side.
Communications between client and server based on ssh connection with linux server or powershell with window server.

II. Setup environment

Before you use Ansible's command, you have to setup ssh on the remote machine.

1. In this learning, I use Ubuntu OS 14.04 LTS. My users are administrator on both servers (remote and control machines) 

2. Config ubuntu server to allow running the sudo command without promt your password (in the remote machines)
    $sudo visudo
    Edit the following line:
        %sudo   ALL=(ALL:ALL) ALL
    to
        %sudo   ALL=(ALL:ALL) NOPASSWD:ALL

3. Setup ssh-copy-id from control machine to remote machine (in the control machine)
   $ssh-copy-id administrator@<Remote-machine-IP>
   After that, you enter your credentials and done.

In the continuous steps, let's setup the ssh-agent to remember your credentials (in the control machine)
   $ ssh-agent bash
   $ ssh-add ~/.ssh/id_rsa
    
Now, erverything are done for you to use the add-on commands
