# Setting up Passenger and Nginx to Autostart

Source: http://serverfault.com/a/69753

This describes how to set up nginx to autostart on Ubuntu when it's installed via RVM and Passenger.

The typical way to start nginx is through /opt/nginx/sbin/nginx assuming that it's installed in the default directory.

* Create shell script in /etc/init.d  
    `sudo vim /etc/init.d/nginx-passenger.sh`

* Paste in this text:

    ```
    #!/bin/bash
    # this script starts the nginx process attached to passenger
    sudo /opt/nginx/sbin/nginx
    ```


* Make it executable
   `sudo chmod +x /etc/init.d/nginx-passenger.sh`

* Run it to make sure it works

* Update the init script links
    `sudo update-rc.d nginx-passenger.sh defaults`

    The man page for update-rc.d is -> http://manpages.ubuntu.com/manpages/hardy/man8/update-rc.d.8.html



