# pg-lb-namespace
Postgres LoadBalance Namespace: It contains the patch to add multiple disk under single namespace in postgres and use those disks to loadbalance the relations.
Single relation will be associated with one disk, not divided/sharded across disks. If we have two relations in database created using 'lb_global' backed by two disk, each relation will be loadbalanced across disks.

###### How to build with postgres
Clone the postgres 14 source code and apply the `0001-Adding-support-to-add-multiple-disk-under-single-Nam.patch` patch. Configure and build the code.

###### How to use
Use LB_DIRS env to set lb_dirs as part of initdb command. `export LB_DIRS=<dir1>,<dir2>,` Suffix need to have `,`
Use 'lb_global' namespace while creating table, index or database. 
