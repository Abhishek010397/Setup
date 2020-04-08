#    Something to notice:

   ##  while executing main.yml file
          
            ansible-playbook main.yml -i hosts
            at the section of 
                
                  name: ensure redis service is restarted
                   it throws an error in the controller while if we run systemctl status redis-server.service on the node it's perfectly
                   fine over there.
          
          
          ERROR:
          
                 fatal: [3.135.221.181]: FAILED! => {"changed": false, "msg": "Unable to start service redis: Warning: The unit file, source configuration file or drop-ins of redis.service changed on disk. Run 'systemctl daemon-reload' to reload units.\nJob for redis-server.service failed because the control process exited with error code.\nSee \"systemctl status redis-server.service\" and \"journalctl -xe\" for details.\n"}

           on the node if we do:
            
                  sudo systemctl status redis
               
            output:
            
                  ● redis-server.service - Advanced key-value store
                   Loaded: loaded (/lib/systemd/system/redis-server.service; enabled; vendor pre
                   Active: failed (Result: exit-code) since Wed 2020-04-08 20:58:12 UTC; 50s ago
                   Docs: http://redis.io/documentation,
                   man:redis-server(1)
                   Process: 7981 ExecStart=/usr/bin/redis-server /etc/redis/redis.conf (code=exit
                   Main PID: 24791 (code=exited, status=0/SUCCESS)

                   Apr 08 20:58:12 ip-172-31-1-240 systemd[1]: redis-server.service: Service hold-o
                   Apr 08 20:58:12 ip-172-31-1-240 systemd[1]: redis-server.service: Scheduled rest
