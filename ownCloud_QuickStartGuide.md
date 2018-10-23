
# ownCloud Quick Start Guide

ownCloud is an open source file sync and share solution that aims to create your own on-premise cloud. It allows you to synchronize information between devices, share files, and collaboratively work on documents. It can be used for small workgroups or departments, mid-sized enterprises, large enterprises, and service providers. Using ownCloud, IT can manage the company‘s confidential documents and allow users to access the required information anytime and anywhere (based on the privileges).

**Topics**:
* [Audience and Purpose](#audience-and-purpose)
* [Getting Started with ownCloud](#getting-started-with-owncloud)
* [Installation Highlights](#installation-highlights)
* [Prerequisites](#prerequisites)
* [Installing ownCloud Server](#installing-owncloud)
* [Configuring ownCloud Server](#configuring-owncloud-server)
* [Installing ownCloud Clients](#installing-owncloud-clients)
* [Connecting to ownCloud Server Using Desktop](#connecting-to-owncloud-server-using-desktop)
* [Connecting to ownCloud Server Using Mobile App](#connecting-to-owncloud-server-using-mobile-app)

## Audience and Purpose
This document is intended for the following users:
* Administrators: Install and Configure ownCloud Server
* Users: Connect to ownCloud Server using the ownCloud client—Desktop client or Mobile App    
[Go to top](#owncloud-quick-start-guide)

## Getting Started with ownCloud      

To get started with ownCloud, perform the following:
* **Review basic ownCloud information**: Read the basic information to understand ownCloud. For more information, see [https://owncloud.org/](https://owncloud.org/)
* **Plan ownCloud installation**: Based on the environment and IT infrastructure, determine your ownCloud Server installation method and the client to connect with the ownCloud Server. For more information, see [https://doc.owncloud.org/server/latest/admin_manual/installation/deployment_recommendations.html](https://doc.owncloud.org/server/latest/admin_manual/installation/deployment_recommendations.html)
* **Procure licenses**: Standard, Enterprise, and custom subscriptions are available. For more information, see [https://owncloud.com/pricing/](https://owncloud.com/pricing/) 
* **Manage ownCloud**: Based on the defined classification, administrators can set document classification rules and enforce it. For more information, see [https://owncloud.com/manage-control-files/](https://owncloud.com/manage-control-files/)      
[Go to top](#owncloud-quick-start-guide)

## Installation Highlights     
   
The following are the steps to install and configure ownCloud Server to connect from a client:
1. Download ownCloud Server.
2. Install ownCloud Server.   
3. Configure ownCloud Server.
4. Install the required client (Desktop or Mobile App) for connecting to the ownCloud Server.
5. Connect to ownCloud Server from client.       
[Go to top](#owncloud-quick-start-guide)

## Prerequisites

Before installing ownCloud, you must consider a few system requirements for the following:     

**Note**: LAMP stack is a combination of an operating system, Web server, database, and PHP. ownCloud requires a LAMP stack to function appropriately. 

* Operating System for server and client
* Database
* Web server
* PHP Runtime version
* Mobile App 
* Browsers and Hypervisors

For more information, see [https://doc.owncloud.org/server/latest/admin_manual/installation/system_requirements.html](https://doc.owncloud.org/server/latest/admin_manual/installation/system_requirements.html)       
[Go to top](#owncloud-quick-start-guide)

## Installing ownCloud Server
1. You can download ownCloud Server using any one of the following resources:
   * Tarball 
   * Docker 
   * Appliance
   * Linux Distribution Packages
   For details about each resource, see [https://owncloud.org/download/](https://owncloud.org/download/)

2. You can install ownCloud Server in any of the following ways:
   * **Using source tarball**: If there are no packages for the Linux distribution, then install the ownCloud Server using the source tarball.     
     **Note**: This is the recommended option for production environments.      
	
	   To install using the source tarball:
        1. Install the required and recommended modules.
        2. Install ownCloud Server.
        3. Configure Web Server.
        4. Enable SSL.
        5. Run the Installation Wizard.
        6. Set strong directory permissions.
        7. Configure SELinux.
        8. Configure core PHP settings.
        9. Configure PHP-FPM (optional).
       10. Configure other Web servers (optional). 
       
       For more information, see [https://doc.owncloud.org/server/latest/admin_manual/installation/source_installation.html](https://doc.owncloud.org/server/latest/admin_manual/installation/source_installation.html)

   * **Using Linux Distribution Packages**: ownCloud provides ready-to-deploy packages for Linux distributions such as 
       Debian, Ubuntu, Fedora, RedHat Enterprise Linux, CentOS and openSUSE.       
	   
	   To install the Linux packages:
       1. Download and install the packages using Linux Package Manager.    
          For more information, see [https://doc.owncloud.org/server/latest/admin_manual/installation/linux_installation.html](https://doc.owncloud.org/server/latest/admin_manual/installation/linux_installation.html)
       2. Run the Installation Wizard to complete the ownCloud Server installation.      
          For more information, see [https://doc.owncloud.org/server/latest/admin_manual/installation/installation_wizard.html](https://doc.owncloud.org/server/latest/admin_manual/installation/installation_wizard.html)
   * **Using Docker image**: Install ownCloud using the ownCloud Docker image. It is designed to work with a data volume in the host filesystem and separate MariaDB and Redis containers. Also, the ownCloud Docker image:
       * Allows ports 80 and 443 for HTTP and HTTPS connections
       * Mounts data and MySQL data directories on the host for persistent storage
   
      To install using Docker image:
      1. Create a new project directory. 
      2. Download docker-compose.yml from the ownCloud Docker GitHub repository into the new directory.
      3. Create an .env configuration file that has the required configuration settings.
      4. Start the container, using your preferred Docker command-line tool.
      5. Check whether all the containers are started successfully.
       
      For more information, see [https://doc.owncloud.org/server/latest/admin_manual/installation/docker/](https://doc.owncloud.org/server/latest/admin_manual/installation/docker/)

  * **Using Appliance**: It is built on Univention Corporate Server (UCS) that is completely configured with a secure 
      connection and the ownCloud Proxy app.       
  
    **Note**: This is recommended for the non-technical users.
    
     To install using Appliance:
     1. Download and install the appliance.
     2. Start the Appliance.
     3. Activate the Appliance.       
     For more information, see [https://doc.owncloud.org/server/latest/admin_manual/appliance/installation.html](https://doc.owncloud.org/server/latest/admin_manual/appliance/installation.html)

 * **Using Command Line**: This method is recommended for scripted operations and system administrators who prefer using 
     command line instead of GUI. 
                                                                                           
     To install using command line:
     1. Download and unpack the source.
     2. Install using the occ command.
     3. Set the correct owner and permissions.
     4. Perform post installation tasks.   
                                
    For more information, see [https://doc.owncloud.org/server/latest/admin_manual/installation/command_line_installation.html](https://doc.owncloud.org/server/latest/admin_manual/installation/command_line_installation.html)          
[Go to top](#owncloud-quick-start-guide)

## Configuring ownCloud Server
After installing the ownCloud Server, the administrator must perform the following basic configurations so that users can connect to this Server from their Desktop client or mobile device: 
 * **Configure database**: All administrative data is stored in the database. 
     To configure the database:
     * Convert database type
     * Configure a supported database such as MySQL/MariaDB, PostgreSQL, or Oracle (ownCloud Enterprise edition only).    
       
     For more information, see [https://doc.owncloud.org/server/latest/admin_manual/configuration/database/](https://doc.owncloud.org/server/latest/admin_manual/configuration/database/) 

* **Configure file sharing options**: You can configure the following file sharing options:
    * Setup file sharing policy
    * Configure Federation sharing
    * Set maximum file size limit
    * Provide default files and folders for new users
    * Configure external storage support
    * Configure encryption
    * Enable transactional file locking
    * Configure previews
    * Control file versions       

    For more information, see 
    [https://doc.owncloud.org/server/latest/admin_manual/configuration/files/file_sharing_configuration.html](https://doc.owncloud.org/server/latest/admin_manual/configuration/files/file_sharing_configuration.html)
 
* **Implement an LDAP proxy cache server**: To reduce network traffic overhead and improve ownCloud performance, 
    implement the LDAP proxy cache. 

    To setup LDAP proxy cache server:
    1. Install OpenLDAP.
    2. Configure the server.
    3. Edit the default configuration directory.
    4. Perform a test search.
    5. Check the logs.
    6. Configure ownCloud LDAP app.   

    For more information, see 
    [https://doc.owncloud.org/server/latest/admin_manual/configuration/ldap/ldap_proxy_cache_server_setup.html](https://doc.owncloud.org/server/latest/admin_manual/configuration/ldap/ldap_proxy_cache_server_setup.html) 

* **Configure Server Operations**: During ownCloud Server installation, most of the server operations are configured automatically. The ownCloud Server has a   
    built-in configuration check that provides a report as warnings at the top of your Admin page. The installer creates the config/config.php file automatically and contains the parameters that controls the server operations.         
	
	**Note**: It is recommended to edit this file only if you have to change a parameter value. For example, to enable 
    users for connecting to the Server using the Server’s IP address and port 8080, change the dbhost parameter to 
    [ServerIPaddress]:[portnumber].        
	
	The following are a few server operations that you can configure:
	* SSL-enabled security     
	* Email notifications    
	* Virus scanner     
	* Memory caching     
	* Background jobs     
	* Activity app    
	
    For more information, see [https://doc.owncloud.org/server/latest/admin_manual/configuration/server/](https://doc.owncloud.org/server/latest/admin_manual/configuration/server/)

* **Manage MIME types**: You can create alias and map file extensions for MIME types. It allows to display custom icons 
    for files. 
    You can perform the following:
    * Change existing icons and use custom icons
    * Map a file extension to a mime type

   For more information, see [https://doc.owncloud.org/server/latest/admin_manual/configuration/mimetypes/](https://doc.owncloud.org/server/latest/admin_manual/configuration/mimetypes/)

* **User Management**: User management enables administrators to manage users and groups based on roles and privileges. 
    You can perform the following:
    * Create, edit, or delete user 
    * View and set quotas for each user
    * Reset passwords
    * Manage groups
    * Enable custom groups
    * Configure user authentication with IMAP, SMB, and FTP
    * Configure user authentication with LDAP
    * Configure Provisioning API app

    For more information, see [https://doc.owncloud.org/server/latest/admin_manual/configuration/user/user_configuration.html](https://doc.owncloud.org/server/latest/admin_manual/configuration/user/user_configuration.html) 
[Go to top](#owncloud-quick-start-guide)

## Installing ownCloud Clients
Users can upload, download, and interact with the ownCloud Server files using the clients.
1. Based on your requirement, you can download any one of the following clients:
   * Desktop client: Synchronizes data from your local system with the ownCloud Server and vice-versa. For more 
     information, see [https://owncloud.org/download/#owncloud-desktop-client](https://owncloud.org/download/#owncloud-desktop-client)    
   **Note**: Supported operating systems are Windows, Mac, and Linux.     
   * Mobile Apps: Synchronizes data from your mobile device with the ownCloud Server and vice-versa. For more information, see [https://owncloud.org/download/#owncloud-mobile-apps](https://owncloud.org/download/#owncloud-mobile-apps)        
   **Note**: Supported operating systems are iOS and Android.     
2. To install ownCloud client:
   * Desktop client: Installation procedures for Mac OS X and Windows are the same. However, Linux users must follow 
     the instructions on the download page.    
     For more information, see [https://doc.owncloud.org/desktop/latest/installing.html](https://doc.owncloud.org/desktop/latest/installing.html) 
   * Mobile Apps: You can install mobile apps for a simple interface, automatic synchronization of the files, and 
     easy to upload files from your device to ownCloud Server. 
     * For more information about installing ownCloud iOS App, see [https://doc.owncloud.org/ios/ios_app.html](https://doc.owncloud.org/ios/ios_app.html)
     * For more information about installing ownCloud Android App, see [https://doc.owncloud.org/android/android_app.html](https://doc.owncloud.org/android/android_app.html)
[Go to top](#owncloud-quick-start-guide)

## Connecting to ownCloud Server Using Desktop
To connect to ownCloud Server from your Desktop:
1. Launch ownCloud Desktop Synchronization Client from your system. 
2. Specify the ownCloud Server URL and login credentials.
3. Select the folders on your system that must be synchronized with the ownCloud Server and vice-versa.
4. Click **Connect**.   
   After the connection is established, the specified folders are synchronized between the ownCloud Server and your 
   system.   
   For more information, see [https://doc.owncloud.org/desktop/latest/](https://doc.owncloud.org/desktop/latest/)
[Go to top](#owncloud-quick-start-guide)

## Connecting to ownCloud Server Using Mobile App
To connect to ownCloud Server using your mobile device:
1. Open the ownCloud app. 
   The **Configuration** screen is displayed.
2. Specify your ownCloud Server URL and login credentials. 
3. Click **Connect**.    
   If the ownCloud Server has a self-signed SSL certificate, a warning message is displayed indicating that it must not be trusted. Tap YES to accept the certificate and complete your account setup. 
   After connecting to the ownCloud Server, the files are synchronized between the ownCloud Server and your mobile device.     
   For more information, see [https://doc.owncloud.org/ios/ios_app.html](https://doc.owncloud.org/ios/ios_app.html) and [https://doc.owncloud.org/android/android_app.html](https://doc.owncloud.org/android/android_app.html)
[Go to top](#owncloud-quick-start-guide)
