Final task
==============
## Descriptions
This vagrant creates a vm, install and deploys a stand with WordPress. In this stand, a bunch of nginx + mysql 8 + php-fpm is used. This site is accessible via the https protocol. By default, the site rises with the wordpress.loc address. In order to check, you need to add this address to hosts on the client.

## Variables
mysql_root_password: "Qwer1234!"
mysql_user_password: "wordpressuser"
mysql_user: "wordpressuser"
mysql_db: "wordpress"
domain: "wordpress.loc"

## Setup and run
* **Step 1**: Using Command Terminal, download and install: ```git clone https://github.com/rxsd20/final_task.git```

* **Step 2**: Go to the directory with command: ```cd final_task```

* **Step 3**: Run the command: ```vagrant up```

* **Step 4**: Go in VM command: ```vagrant ssh```

* **Step 5**: Enter command: ``` ```

* **Step 6**: Exit VM: ```exit```


## Vagrant Commands
* **Start VM**: ```vagrant up```
* **Hibernate VM**: ```vagrant suspend```
* **Restart VM**: ```vagrant reload```
* **Destroy VM**: ```vagrant destroy```
* **Remove from Vagrant Box List**: ```vagrant box remove centos/7```

#### SSH Info
* User: vagrant
* Password: vagrant
