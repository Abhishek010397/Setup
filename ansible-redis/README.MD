#    Something to notice:

   ##  while executing main.yml file
          
            ansible-playbook main.yml -i hosts
            at the section of 
                
                  name: ensure redis service is restarted
                   it throws an error in the controller while if we run systemctl status redis-server.service on the node it's perfectly
                   fine over there.
          
          
          ERROR:
          
                 fatal: [3.135.221.181]: FAILED! => {"changed": false, "msg": "Unable to start service redis: Warning: The unit file, source configuration file or drop-ins of redis.service changed on disk. Run 'systemctl daemon-reload' to reload units.\nJob for redis-server.service failed because the control process exited with error code.\nSee \"systemctl status redis-server.service\" and \"journalctl -xe\" for details.\n"}
