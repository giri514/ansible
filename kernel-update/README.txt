***********************************************************************************************************************
***********************THIS PLAYBOOK WILL UPDATE THE KERNEL VERSIONS FOR A GROUP OF INSTANCES**************************
***********************************************************************************************************************
*                                                                                                                     *
*  In order to run this playbook, you will need to follow below instructions:                                         * 
*                                                                                                                     *
*      1. Need to establish the connection with the instances by adding the entries for instances under the group     *
*         "[webservers]" in the file "/etc/ansible/hosts".                                                            *
*                                                                                                                     *
*      EXAMPLE ENTRY:                                                                                                 *
*                    [webservers]                                                                                     *
*                    instance ansible_host=130.211.112.221 ansible_user=root                                          *                       
*                    instance-1 ansible_host=34.121.47.186 ansible_user=root                                          *
*                                                                                                                     *
*      2. After adding entries for instances under the group "[webservers]", please run below command on ansible      *
*         sever for each instance added under the group                                                               *
*                                                                                                                     *
*         "ssh-copy-id root@130.211.112.221"                                                                          *
*                                                                                                                     *
*         NOTE: You need to replace the IP in the above command with the IP of actual instance and then enter the     *
*         password for the instance. Once done, you can check the connectivity with the instance from ansible server  *
*         by running the command e.g. "ansible -m ping instance_name"                                                 *
*                                                                                                                     *
*  When you run the playbook script, it will prompt for below:                                                        *
*                                                                                                                     *
*              DO YOU WISH TO UPDATE THE KERNEL VERSIONS ON ALL THE INSTANCES? (yes/no):                              *
*              DO YOU WISH TO REBOOT ALL THE INSTANCES AFTER KERNEL UPDATES? (yes/no):                                *
*                                                                                                                     *
***********************************************************************************************************************
***********************************************************************************************************************
