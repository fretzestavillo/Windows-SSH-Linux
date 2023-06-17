- This exercise teach on how to install ssh and connect on the server using Secure Shell protocol
- In this example I have two computers that have a different operating system which is windows(ssh client) and Linux(ssh server).

First I install ssh in linux computer.
- Open the terminal application.
  Type the command below:
    $ sudo apt-get update
    $ sudo apt-get upgrade
    $ sudo apt-get install openssh-client

- To Enable SSH Server on Linux
- Open your terminal application
- Install the openssh-server package on Ubuntu
- Type the command below:
- $ sudo apt install openssh-server
- Enable ssh server on Ubuntu
- Type the command below:
- $ sudo systemctl enable ssh

-  By default, firewall will block ssh access. Therefore, you must go to https://www.cyberciti.biz/faq/howto-configure-setup-firewall-with-ufw-on-ubuntu-linux/ and open ssh port

- By default ufw is inactive status. In other words, no firewall rules configured and all traffic allowed. To see status, Type the command below:
- $ sudo ufw status
- Sample outputs:
- Status: inactive

- Set up a UFW firewall with default policy
- By default when the ufw activated it blocks all incoming traffic to the firewall/server. Only outgoing traffic allowed. You can view UFW’s    - -  - defaults by typing the following command:
- $ grep 'DEFAULT_' /etc/default/ufw
-  Sample outputs:
- DEFAULT_INPUT_POLICY="DROP"
- DEFAULT_OUTPUT_POLICY="ACCEPT"
- DEFAULT_FORWARD_POLICY="DROP"
- DEFAULT_APPLICATION_POLICY="SKIP"

-  The default policy works out well for both the servers and laptop/workstation as you only need to open a limited number of incoming ports. It is a good policy as it closes all ports on the server/firewall and you need to only open ports one by one. You can run the following commands to set policy to block all incoming connection and only allow outgoing connections from the server/firewall:
- $ sudo ufw default allow outgoing
- $ sudo ufw default deny incoming

- Writing your first firewall rule to allow connection to ssh (tcp port 22)
- Type the following command to allow SSH connections to your server:
- $ sudo ufw allow 22/tcp

- Enable the UFW based firewall
- Now you have default policy and ssh port allowed. It is safe to start enable the firewall, enter:
- $ sudo ufw enable
- Sample outputs:
- Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
- Firewall is active and enabled on system startup

- How do I check the status of my rules?
- Use the status command:
- $ sudo ufw status
- $ sudo ufw status verbose

- How to start/stop/restart SSH service on Ubuntu
- The syntax is:
- $ sudo systemctl start ssh
- $ sudo systemctl stop ssh
- $ sudo systemctl restart ssh
    
- To view status, run:
- $ sudo systemctl status ssh












