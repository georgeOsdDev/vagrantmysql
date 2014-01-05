# simple mysql-server

1. `git clone https://github.com/georgeosddev/vagrantmysql.git`
2. `cd vagrantmysql`
3. `vagrant up`

**Notice**

This error will happen at first

		/usr/bin/chef-solo:19
		[2014-01-05T08:45:12+01:00] ERROR: Running exception handlers
		[2014-01-05T08:45:12+01:00] ERROR: Exception handlers complete
		[2014-01-05T08:45:12+01:00] FATAL: Stacktrace dumped to /var/chef/cache/chef-stacktrace.out
		[2014-01-05T08:45:12+01:00] FATAL: Chef::Exceptions::GroupIDNotFound: directory[/var/log/mysql] (mysql::_server_rhel line 11) had an error: Chef::Exceptions::GroupIDNotFound: cannot determine group id for 'mysql', does the group exist on this system?
		Chef never successfully completed! Any errors should be visible in the
		output above. Please fix your recipes so that they properly complete.

So retry

`vagrant provision`

Connect to mysql from Host OS.

`bin/mysql -u root -h mysql.local -p` (password=p@ssw0rd)

