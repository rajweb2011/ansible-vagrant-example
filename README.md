# ansible-vagrant-example
ansible-vagrant-example

i have tested this example in mac 
1. cd ansible-vagrant-example and vagrant up 
2. it will spinup 4 hosts webhost1 and 2 and dbhost1 and 2 
3. run command vagrant ssh-config and copy your private key path  and paste/replace in your inventory keypath=

pre-task -  add your host know keys with just login to vagrant machines like below 
ssh vagrant@172.17.178.21   when prompt enter password as "vagrant" accpet store key in your local host
ssh vagrant@172.17.178.22   when prompt enter password as "vagrant" accpet store key in your local host
ssh vagrant@172.17.178.23   when prompt enter password as "vagrant" accpet store key in your local host
ssh vagrant@172.17.178.24   when prompt enter password as "vagrant" accpet store key in your local host

4. RUN your fist play book 
 ansible-playbook --limit="all" --inventory-file=inventery -v playbook.yml
 
 
5. output will be similar like below 

ansible-playbook --limit="all" --inventory-file=inventery -v playbook.yml                                                    
No config file found; using defaults

PLAY [web_nodes] ******************************************************************************************************************************************************************************************

TASK [Gathering Facts] ************************************************************************************************************************************************************************************
ok: [webnode1]
ok: [webnode2]
ok: [dbnode1]

TASK [Update apt-cache] ***********************************************************************************************************************************************************************************
changed: [webnode1] => {"changed": true, "cmd": ["id"], "delta": "0:00:00.002849", "end": "2020-04-28 19:19:20.570922", "rc": 0, "start": "2020-04-28 19:19:20.568073", "stderr": "", "stderr_lines": [], "stdout": "uid=0(root) gid=0(root) groups=0(root)", "stdout_lines": ["uid=0(root) gid=0(root) groups=0(root)"]}
changed: [webnode2] => {"changed": true, "cmd": ["id"], "delta": "0:00:00.002500", "end": "2020-04-28 19:19:20.584778", "rc": 0, "start": "2020-04-28 19:19:20.582278", "stderr": "", "stderr_lines": [], "stdout": "uid=0(root) gid=0(root) groups=0(root)", "stdout_lines": ["uid=0(root) gid=0(root) groups=0(root)"]}
changed: [dbnode1] => {"changed": true, "cmd": ["id"], "delta": "0:00:00.002614", "end": "2020-04-28 19:19:20.595914", "rc": 0, "start": "2020-04-28 19:19:20.593300", "stderr": "", "stderr_lines": [], "stdout": "uid=0(root) gid=0(root) groups=0(root)", "stdout_lines": ["uid=0(root) gid=0(root) groups=0(root)"]}

TASK [my script is running now .....] *********************************************************************************************************************************************************************
changed: [webnode1] => {"changed": true, "rc": 0, "stderr": "Shared connection to 172.17.178.21 closed.\r\n", "stderr_lines": ["Shared connection to 172.17.178.21 closed."], "stdout": "You are root.\r\n", "stdout_lines": ["You are root."]}
changed: [webnode2] => {"changed": true, "rc": 0, "stderr": "Shared connection to 172.17.178.22 closed.\r\n", "stderr_lines": ["Shared connection to 172.17.178.22 closed."], "stdout": "You are root.\r\n", "stdout_lines": ["You are root."]}
changed: [dbnode1] => {"changed": true, "rc": 0, "stderr": "Shared connection to 172.17.178.23 closed.\r\n", "stderr_lines": ["Shared connection to 172.17.178.23 closed."], "stdout": "You are root.\r\n", "stdout_lines": ["You are root."]}

PLAY RECAP ************************************************************************************************************************************************************************************************
dbnode1                    : ok=3    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
webnode1                   : ok=3    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
webnode2                   : ok=3    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0


