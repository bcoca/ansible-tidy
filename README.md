Tidy
====

A role to 'tidy up' a directory, feed it a path and a list of files that should be there and it will remove all the files that should not be there.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

###Required

* tidy_path: the path to the directory to 'tidy up', i.e `/etc/apache2/conf.d`
* tidy_expected: list of files that 'should be there', i.e `['vhost1.conf', 'vhost2.conf']`

###Optional

* tidy_handler: A handler that will execute if files are deleted, it could use the `tidy_removed` var that cointains the deleted file list (`default: tidy_show`, prints the list to screen)


###Registered

* tidy_existing: list of files that existed in path, (default: [])
* tidy_removed: list of files removed, (default: [])

Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: webservers
      roles:
         - { role: briancoca.tidy, tidy_path: /etc/apache2/conf.d, tidy_expected: ['vhost1.conf', 'vhost2.conf'], tidy_handler: mailme}

License
-------

GPLv3

