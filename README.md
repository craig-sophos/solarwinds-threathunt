# solarwinds-threathunt


The query takes a CSV file published by SOPHOS Security based on Fireeye published IOCs and parses out the IOCs, then performs a hunt. Note you have to setup the variables and use the RAW csv file in Sophos Central.

To test it you can drop an executable in the C:\PerfLogs directory and run it.  Putting executables in that directory will be a deteced IOC.
## Test it
If you drop any executable in the C:\PerfLogs\ directory and run the query it should show it as a MATCH for one of the IOC's  If that is not happening you will want to ensure that the CURL command to the git repository is working.

## Any issues
Determine if the CURL is returning a result or not
SELECT * FROM curl WHERE url = 'https://raw.githubusercontent.com/sophoslabs/IoCs/master/Ransomware-Ryuk.csv'
That should return a single row with a 200 for response and a large data blob in the 'results' column.  If it is not then the Device may still be able to reach the internet but something is preventing osquery service from doing the same.  It may be a problem at the ISP, GIT or your own firewall rules, potentially identifying the content of the CSV as MAL or some other rule.


https://raw.githubusercontent.com/sophoslabs/IoCs/master/Ransomware-Ryuk.csv
VARIABLES:
VARIABLE 

|TYPE  | 	VALUE  |   
|---|---|---|
| Number of Hours of activity to search  | STRING | 24 |  
|  RAW IOC List location from a URL|STRING|72 | 
|Start Search From | DATE | 06/06/2020 12:00:00 |

