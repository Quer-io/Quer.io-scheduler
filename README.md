#Querio Scheduler
A scheduler for retraining saved [Querio](https://github.com/quer-io/quer.io) models periodically.
##Installation
* If you don't have the Querio package, install it from [https://github.com/quer-io/quer.io](https://github.com/quer-io/quer.io).
* In a console window, install requirements with
 ~~~~
 pip install -r requirements.txt
 ~~~~
##Usage
The scheduler can be given the preferred time to retrain and the path to saved models.  
* The default time is 02:00 and the default path is the current directory. 
* Path is formatted with forward slashes: "path/to/models".
* Time is input in HH:MM format: "23:04".  
When running, the scheduler can be stopped by pressing CTRL + C.  
###As a script:
In a console window, run with
 ~~~~
 python scheduler.py
 ~~~~
 Optional arguments:
 ~~~~
 -t [HH:MM]
 -p [/path/to/models]
 --now    (retrains the models immediately and then exits)
 --help   (shows usage instructions)
 ~~~~
 
 For example:
 ~~~~
 python scheduler.py -t "23:04" -p "/path/to/models"
 ~~~~
###As a python module:
In a Python shell, import and initialize the scheduler with
 ~~~~
 import querio_scheduler as qs
 scheduler = qs.Scheduler(db_path, user)
 ~~~~
The scheduler can be given the preferred time and path to saved models.  
* The default time is 02:00 and the default path is the current directory. 
* Path is formatted with forward slashes: "path/to/models".
* Time is input in HH:MM format: "23:04".

The parameters can be given on init
 ~~~~
 scheduler = qs.Scheduler("path/to/models", "23:04")
 ~~~~ 
 or with
  ~~~~
 scheduler.set_path("path/to/models")
 scheduler.set_time("23:04")
 ~~~~ 
 Start the scheduler with
 ~~~~
 scheduler.run()
 ~~~~
 Or simply retrain all the models immediately with:
 ~~~~
 scheduler.retrain()
 ~~~~
