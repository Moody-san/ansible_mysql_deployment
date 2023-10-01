You'll also need add the following content MySQL 
configuration file named master_master.cnf:

[mysqld]
server-id = 1  # Change this value on the second server to 2
log_bin = /var/log/mysql/mysql-bin.log
binlog_do_db = my_database_name  # Replace with your database name


run the following command to execute:
ansible-playbook -i <path_to_inventory_file> mysql_master_master.yml --extra-vars "mysql_root_password=<your_root_password> replication_user=<replication_username> replication_password=<replication_password> replication_host=<second_server_ip>"
