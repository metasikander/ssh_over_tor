# ssh_over_tor
An ansible role to set up ssh server over the onion router (tor)

# Disclamer
This role was created without any considerations on best practices or any form of hardening of the system.  
Use at your own discretion.

# What it does
This role will make sure that ssh server is installed and running.  
Then it will make sure that a firewall is installed, and set up to allow port 22 (ssh) and 9050 (tor).  
Then it will install and set up tor to share the ssh-connection, and lastly print the onion-address.

# How to connect
Install tor on your system.  
The program torify will come with the package, and this is what you use to connect to the server.  
Like this:  
```
$ torify ssh [username]@[onion-address]

# Example
$ torify ssh metasikander@hmrmtpqebj62j7maqm5glp6iz5fw4x4jcwnintacyqvaegj3wdf3tyyd.onion
```

# Example Playbook

    - hosts: servers
      become: true
      roles:
         - metasikander.ssh_over_tor

# License

MIT