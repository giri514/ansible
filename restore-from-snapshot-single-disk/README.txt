*********************************************************************************************************
***********This Playbook will be used to restore the Plesk instance with 2 disks from snapshots**********
*********************************************************************************************************
*                                                                                                       *
* 1. Before running the playbook, please note down the below details of existing/crashed instance:      *
*                                                                                                       *
*    Instance Name                                                                                      *
*    Instance Label                                                                                     *
*    Public IP                                                                                          *
*    Private IP                                                                                         * 
*    Machine Type                                                                                       *
*    OS disk size                                                                                       *
*    Customer data disk size                                                                            *
*    Instance Region                                                                                    *
*    Instance Zone                                                                                      *
*                                                                                                       *
* 2. Un-assign Public IP of existing/crashed instance, but do not release it and shut it down           *
*                                                                                                       *
* 3. Note down the selfLinks of OS disk and customer data disk snapshots                                *
*                                                                                                       *
* 4. Run the playbook "instance-create-using-snapshot.yml" and it will prompt for below:                *
*                                                                                                       *
*        Please enter the Instance Name:                                                                *
*        Please enter the instance brand i.e. hostgrid or hostplus or sitecreator:                      *
*        Please enter the machine_type e.g. n1-standard-1 [1 vCPU and 3.75 GB], etc:                    *
*        Size in GB for OS disk:                                                                        *
*        Size in GB for customer data disk:                                                             *
*        Please enter the Region:                                                                       *
*        Please enter the Zone:                                                                         *
*        Please enter the SelfLink for OS disk Snapshot:                                                *
*        Please enter the SelfLink for customer data disk Snapshot:                                     *
*        Please enter the Private IP of Old/crashed instance:                                           *
*                                                                                                       *
* 5. Make sure that same Public IP assigned to the new instance otherwise, assign it manually           *
*                                                                                                       *
* Note that the instance will be provisioned with different Private IP and Nginx will not start. So,    *
* this playbook will switch the domains from Old Private IP to the new one.                             *
*                                                                                                       *
* If the task "Switch all the domains on new Private IP" failed for some reason then you will have to   *
* perform below steps manually:                                                                         *
*                                                                                                       *
*    A. Try to switch all the domains by running the script "/home/ansible/updatedomains.sh"            * 
*    B. Once all domains switched over to the new Private IP, remove old instance Private IP from Plesk *
*    C. Run command "plesk repair web -domains-only" to re-generate nginx config files for all domains  *
*    D. Start the nginx service                                                                         *
*                                                                                                       *
* 6. Assign snapshot schedule to the new disks                                                          *
*                                                                                                       *
*********************************************************************************************************
*********************************************************************************************************
