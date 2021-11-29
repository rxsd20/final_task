Lesson3 lvm disks tuning
==============
## Descriptions
This vagrant creates a vm, installs the necessary packages to complete the job, expands and upgrade root system, var and home, and also adds mirroring lvm partitions. Create and boot Libvirt domains. Main playbooks are stage1, mirror-lvm, stage2 and stage3.

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
