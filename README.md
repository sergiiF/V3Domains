other
=====
UseCase:


In order to be able to use domains in IceHouse keystone code should be changed.
Research what changes are required to code and to policy.json.
Expected CLI commands to be available:
Cloud admin.
Could admin is a user who is assigned as an admin to domain pointed in /etc/keystone/policy.json in cloud_admin rule
#
As a cloud admin I should be able:

#list users
openstack user list

#list projects
openstack project list --domain <name>

#delete project
openstack project delete <project_id>

#list role assignements
openstack role assignment list --project <project_id>

#list domains
openstack domain list

#create domains
openstack domain create <domain_name>

#delete domain
openstack domain set --disable <domain_name>
openstack domain delete <domain_name>

#add role user->domain
openstack role add --domain <domain_name> --user <user_name> <role>

#remove role user->domain
openstack role remove --domain <domain_name> --user <user_name> <role>

Domain admin.
As a domain admin I should be able:
#Show my domain info
openstack domain show <domain_name>

#list projects in the domain
openstack project list --domain <domain_name>

#create project in the domain
openstack project create --domain <domain_name> <project_name>

#add role user->project
openstack role add --project <project_uuid> --user <user_name> <role>

#remove role user->project
openstack role remove --project <project_uuid> --user <user_name> <role>

#list roles per domain
openstack role assignment list --domain <domain_name>

#list roles per project
role assignment list --project <project_id>
