##Mod_WSGI Monitor

Python3 port of the monitor.py file that allows automagic reloading of the Mod_WSGI Daemon.


###Changes For Python3 Compliance

The code snippet provided [here](https://code.google.com/p/modwsgi/wiki/ReloadingSourceCode#Monitoring_For_Code_Changes) works exceptionally well if you are running python2.x.  There are only two slight issues with the file that needed to be changed to allow for Python3.x compliance.

  * `Queue` has been changed to `queue`.
  * `print` is now a "function" and not a statement.


###Using The monitor.py File With Django

Using the [monitor.py](https://github.com/JenkinsDev/Mod_WSGI-Monitor/blob/master/monitor.py) file with your Django Python3 + Apache (mod_wsgi) project is pretty straight forward.

  1. Add the monitor.py file from this repository into your project's directory.  Your project's directory should be, by default, the directory where your `wsgi.py` file is placed.
  2. Now that the monitor.py file is in place you just need to add the following snippet:
    
  ```py
  import <project_name>.monitor
  <project_name>.monitor.start(interval=1.0)
  ```
  
  Example:
  ```py
  import bmg_email.monitor
  bmg_email.monitor.start(interval=1.0)
  ```
