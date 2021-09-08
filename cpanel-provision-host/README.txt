**********************************************************************************************************************
************************IMPORTANT NOTE: MAKE SURE TO ENTER CORRECT INPUTS IN THE PROMPTS******************************
**********************************************************************************************************************
*  CloudLinux License:                                                                                               *
*                                                                                                                    *
*   - IP Based:   If the license type is IP based then, purchase it right after initiating playbook script           *
*   - Key Based:  In this case, you will have to enter the License Key in the CloudLinux License prompt              *
*                                                                                                                    *
* 1. When you run the playbook script, it will prompt for below:                                                     *
*                                                                                                                    *
* Please enter the Instance Name/Hostname Prefix from the list:                                                      *
* Please enter the suffix for hostname i.e. srv.hostgrid.com or srv.sitecreator.com or srv.hostplus.com:             *
* Please enter instance brand for instance labelling i.e. hostgrid-cpanel or hostplus-cpanel or sitecreator-cpanel:  *
* Please enter the machine_type e.g. n1-standard-1 [1 vCPU and 3.75 GB], etc:                                        *
* OS Disk Size in GB e.g 64:                                                                                         *
* Size in GB for additional disk on which customer data will be stored e.g 256:                                      *
* Please enter the CloudLinux License Key and in case of IP based license just press ENTER:                          *
*                                                                                                                    *
* 2. Once, the main playbook executed completely, purchase and activate cPanel license. Then run the sub playbook:   *
*    "post-cpanel-config.yml" [ In order to run this, need to establish the connection with the instance by adding   *
*    entry in file "/etc/ansible/hosts". Also, add the instance name under "hosts:" section in this playbook ]       *
*    This playbook will perform below operations:                                                                    *
*                                                                                                                    *
*   - Enable cPanel backups                                                                                          *
*   - Move /backup to /home                                                                                          *
*   - Create custom packages                                                                                         *
*   - Disable IMAP, POP and DNS service                                                                              *
*   - Disable DNS and EMAIL options from default feature list                                                        *
*   - Disable Imunify360 and SiteBuilder from cPanel                                                                 *
*   - Set PHP 8.0 as default PHP version                                                                             *
*                                                                                                                    *
* 3. Below will be the manual work after provisioning a instance using playbook:                                     *
*                                                                                                                    *
*   - Reset default root password                                                                                    *
*     [You can get the default root password from the file "group_vars/credentials.yml"]                             *
*   - Buy a Imunify360 license from licensing portal and activate the license on the instance                        *
*   - Add the server in Fortifi >> Resource Manager >> Pools >> cPanel Pool with login details and CPU, Memory,      *
*     Disk size                                                                                                      *
*   - Add the monitoring for the server at https://zabbix.srv.hostgrid.com with template "HostPlus cPanel Template"  *
*   - Assign the snapshot schedule to the disks of instance                                                          *
*                                                                                                                    *
* Note:                                                                                                              *
*   - The playbook will add the instance IP in Site.Pro portal.                                                      *
*                                                                                                                    *
**********************************************************************************************************************
********* Playbook will run for an hour as the cPanel and CloudLinux Installations are time consuming tasks **********     
**********************************************************************************************************************
