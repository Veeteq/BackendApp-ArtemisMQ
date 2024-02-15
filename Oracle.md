# Setup Oracle VirtualBox and Oracle Linux

1. Install Oracle VirtualBox
2. Install Oracle Linux on VirtualBox
3. Configure Host Only Adapter

# Install Database
1. dnf update
2. dnf -y install oracle-database-preinstall-21c
3. download latest XE database from https://www.oracle.com/database/technologies/xe-downloads.html
   
`wget --no-check-certificate https://download.oracle.com/otn-pub/otn_software/db-express/oracle-database-xe-21c-1.0-1.ol8.x86_64.rpm`
 

4. dnf install -y oracle-database-xe-21c-1.0-1.ol8.x86_64.rpm
5. review config file: /etc/sysconfig/oracle—xe–21c.conf
6. run the configuration script: /etc/init.d/oracle-xe-21c configure

| File Name and Location | Purpose |
|--|--|
|`/opt/oracle`|Oracle Base. This is the root of the Oracle Database XE directory tree.|
|`/opt/oracle/product/21c/dbhomeXE`|Oracle Home. This home is where the Oracle Database XE is installed. It contains the directories of the Oracle Database XE executables and network files.|
|`/opt/oracle/oradata/XE`|Database files.|
|`/opt/oracle/diag`  subdirectories|Diagnostic logs. The database alert log is  `/opt/oracle/diag/rdbms/xe/XE/trace/alert_XE.log`|
|`/opt/oracle/cfgtoollogs/dbca/XE`|Database creation logs. The  `XE.log`  file contains the results of the database creation script execution.|
|`/etc/sysconfig/oracle-xe-21c.conf`|Configuration default parameters.|
|`/etc/init.d/oracle-xe—21c`|Configuration and services script.|

https://docs.oracle.com/en/database/oracle/oracle-database/21/xeinl/installing-oracle-database-free.html#GUID-728E4F0A-DBD1-43B1-9837-C6A460432733
https://www.youtube.com/watch?v=kiuIwHxFvpg
