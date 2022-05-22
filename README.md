# Roomba-J7-HA-Integration

To integrate the new Roomba J7 into home assistant, follow the below directions, as the original version of holding down the home button does not work on this particular robot vacuum.

Begin by downloading a .zip file of this GitHub: https://github.com/NickWaterton/Roomba980-Python
Unzip the file, but keep the name of the original zip file.

Enter the newly unzipped file and browse to 'Roomba980-Python-master\Roomba980-Python-master\roomba'
Once you enter that file, you should observe many files ending in .py.
Look for two specific files, "getpassword.py" and "roomba.py"

Once you have found those files, right click on an empty spot in the folder and click, "Open in Windows Terminal."

It should open up a new terminal, in which you should run "py password.py username password" replacing "username" with your Irobot username and "password" with your Irobot password.

If any errors pop up about missing dependencies, run "py -m pip install requests" and rerun the last line of code.

You should then get an output similar to:

py password.py my_email my_password
2022-02-05 14:54:31 INFO [Roomba.Password] Using Password version 2.1
2022-02-05 14:54:31 INFO [Roomba.Password] reading/writing info from config file ./config.ini
2022-02-05 14:54:31 INFO [Roomba.Password] waiting on port: 5678 for data
2022-02-05 14:54:41 INFO [Roomba.Password] Getting Roomba information from iRobot aws cloud...
2022-02-05 14:54:41 DEBUG [urllib3.connectionpool] Starting new HTTPS connection (1): disc-prod.iot.irobotapi.com:443
2022-02-05 14:54:41 DEBUG [urllib3.connectionpool] https://disc-prod.iot.irobotapi.com:443 "GET /v1/discover/endpoints?country_code=US HTTP/1.1" 200 1855
2022-02-05 14:54:41 DEBUG [urllib3.connectionpool] Starting new HTTPS connection (1): accounts.us1.gigya.com:443
2022-02-05 14:54:41 DEBUG [urllib3.connectionpool] https://accounts.us1.gigya.com:443 "POST /accounts.login HTTP/1.1" 200 791
2022-02-05 14:54:41 DEBUG [urllib3.connectionpool] Starting new HTTPS connection (1): unauth2.prod.iot.irobotapi.com:443
2022-02-05 14:54:42 DEBUG [urllib3.connectionpool] https://unauth2.prod.iot.irobotapi.com:443 "POST /v2/login HTTP/1.1" 200 2771
2022-02-05 14:54:42 INFO [Roomba.Password] Got cloud info: {
  "A0592C9921B44542AE00B564D2AF37EE": {
    "password": ":1:324324324324:bababababababababa",
    "sku": "j755020",
    "softwareVer": "sapphire+1.2.12+Firmware-Production+57",
    "name": "Optimus Grime",
    "cap": {
      "binFullDetect": 2,
      "dockComm": 1,
      "wDevLoc": 2,
      "bleDevLoc": 1,
      "edge": 0,
      "maps": 3,
      "pmaps": 5,
      "tLine": 2,
      "area": 1,
      "eco": 1,
      "multiPass": 2,
      "pose": 1,
      "team": 1,
      "pp": 0,
      "lang": 2,
      "5ghz": 1,
      "prov": 3,
      "sched": 1,
      "svcConf": 1,
      "ota": 2,
      "log": 2,
      "langOta": 0,
      "oMode": 2,
      "odoa": 2,
      "expectingUserConf": 1
    },
    "svcDeplId": "v007",
    "user_cert": true
  }
}
2022-02-05 14:54:42 INFO [Roomba.Password] Found 1 roombas defined in the cloud

Look for the line that says something similar to "password": ":1:324324324324:bababababababababa",
Copy the password, excluding quotes, and go to Home assistant.

Begin the integration of a new roomba, in which it should ask for you to hold down the home button.
Click manual password and input the password.

If it asks for a host, find the IP adress your Roomba is on in your network page.

Contact me on reddit at u/xX500_IQXx if you have a problem.
