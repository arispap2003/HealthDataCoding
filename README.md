# HealthDataCoding
Public repository containing common data coding for health data in Greece.

Using Common Data Coding practices improves data integrity and it  <br>
is useful for avoiding data remapping (eg. on double programming) <br>

This set has only the Hospitals in Greece. <br>
The set is unique-proven and easy to find anywhere (because it use their telephone number) <br>

Can be easily used as a library. For example in SAS: <br>

/\* Fetch the file from the repository \*/ <br>
filename probly temp;   <br>
proc http   <br>
url="https://raw.githubusercontent.com/arispap2003/HealthDataCoding/master/hospitals/hospitals.csv"  <br>
method="GET"  <br>
out=probly;  <br>
run;  <br>
/\* Tell SAS to allow "nonstandard" names \*/   <br>
options validvarname=any;   <br>
/\* import to a SAS data set \*/   <br>
proc import  <br>
file=probly  <br>
out=work.probly replace   <br>
dbms=csv;  <br>
run; <br>

(source: https://blogs.sas.com/content/sasdummy/2017/05/07/download-convert-csv-files/)
