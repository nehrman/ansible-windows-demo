<h1>Ansible Window Demo</h1>

<p>This bunch of playbooks aims to provide a quick introduction to Ansible and Windows to demonstrate differents use cases like :
  <ul style="list-style-type:none">
    <li>Manage SQL DB for existing instances</li>
    <li>Manage Active Directory Users</li>
    <li>Manage Active Directory Groups</li>
    <li>Deploy and manage Applications with chocolatey</li>
    <li>Manage Local Groups</li>
    <li>Configure IIS with a basic index.html</li>
  </ul>
</p>

<h2>Manage SQL DB for existing instances:</h2>
<p>To work, you need to install <b>pymssql</b> on the ansible / ansible tower host using pip : <b>pip install pymssql</b>
Because it's using local ansible host to execute the remote SQL command, we define <b>hosts: localhost</b> with <b>connection: local</b></p>
<p>To run this playbook, you need to define those variables :
<ul style="list-style-type:none">  
  <li>db_name: '' => Name of the DB you want to manage (create / import or delete)</li>
  <li>db_host: '' => SQL hostname / IP</li>
  <li>db_host_user: '' => Username that has enough right to create DB on SQL Server</li>
  <li>db_host_pwd: '' => USername's password</li>
  <li>db_state: '' => You could choose present, absent or import (if target is defined in the playbook)</li>
</ul>
</p>
<p><b>Example:</b>
  <ul>
    <li>ansible-playbook managedb.yml -e "db_name=DB db_host=mssqlserver.test.local db_host_user=TEST\user db_host_pwd=*** db_state=present"</li>
  </ul>
</p>

