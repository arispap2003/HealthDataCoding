# HealthDataCoding
Public repository containing common data coding for health data in Greece.

Using Common Data Coding practices improves data integrity and it
is useful for avoiding data remapping (eg. on double programming)

This set has only the Hospitals in Greece.
The set is unique-proven and easy to find anywhere (because it is their telephone number)

Can be easily used as a library. For example in SAS:

/* Fetch the file from the repository */
filename probly temp;
proc http
 url="https://github.com/arispap2003/HealthDataCoding/blob/master/hospitals/hospitals.csv"
 method="GET"
 out=probly;
run;
/* Tell SAS to allow "nonstandard" names */
options validvarname=any;
 
/* import to a SAS data set */
proc import
  file=probly
  out=work.probly replace
  dbms=csv;
run;
(source: https://blogs.sas.com/content/sasdummy/2017/05/07/download-convert-csv-files/)
