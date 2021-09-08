**********************************************************************************************************************
************************IMPORTANT NOTE: MAKE SURE TO ENTER CORRECT INPUTS IN THE PROMPTS******************************
**********************************************************************************************************************
*                                                                                                                    *
* 1. When you run the playbook script, it will prompt for below:                                                     *
*                                                                                                                    *
* Please enter the Instance Name/Hostname Prefix from the list:                                                      *
* Please enter the suffix for hostname i.e. srv.hostgrid.com or srv.sitecreator.com or srv.hostplus.com:             *
* Please enter the instance brand for instance labelling i.e. hostgrid or hostplus or sitecreator:                   *  
* Please enter the machine_type e.g. n1-standard-1 [1 vCPU and 3.75 GB], etc:                                        *
* Size in GB for OS disk e.g 32 ro 64:                                                                               *
* Size in GB for additional disk on which customer data will be stored e.g 256:                                      *
* Please Enter Plesk Activation Code:                                                                                *
*                                                                                                                    *
* 2. Below will be the manual work after provisioning a instance using playbook:                                     *
*                                                                                                                    *
*   - Login to Plesk CP using default password and change Plesk admin password using "Change Password” option.       *
*     [You can get the default Plesk admin password from the file "group_vars/credentials.yml"]                      *
*   - Login to Plesk CP and click on "Hide" button under Site.pro Website Builder >> Other plugin functions section. *   
*   - Update the server hostname at Plesk CP >> Tools & Settings >> SSL/TLS Certificates >> Let's Encrypt            *
*   - Buy a Imunify360 license from Plesk licensing portal and activate the license on the instance                  *
*   - Add the server in Fortifi >> Resource Manager >> Pools >> Plesk Pool with Plesk admin details and CPU, Memory, *
*     Disk size                                                                                                      *
*   - Add the monitoring for the server at https://zabbix.srv.hostplus.com with template "HostPlus Plesk Template"   *
*   - Assign the snapshot schedule to the disks of instance                                                          *
*                                                                                                                    *                                                 
* Note:                                                                                                              *
*   - The playbook will add the instance IP in Site.Pro portal.                                                      *
*                                                                                                                    *
**********************************************************************************************************************
**********************************************************************************************************************
