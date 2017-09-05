**HEAT template for seting up ELK server**

This template can be used to setup a ELK stack on a Openstack VM.
It will create an openstack instance as a boot from volume and setup the necessary security access group for the VM.

Following heat command can be used to create a heat stack:

> heat stack-create -f elk-server.yml -e environment.yml < stack-name >

Please note - I am providing the environment parameters through environment.yml

This heat template can be further used to setup a Murano application using the below commands: 

> murano package-create --template elk-server.yml --name ELK-Server --logo heat.png

> murano --murano-url 'http://< murano server url >:8082' package-import /root/murano-heat-elk/elk-server.zip 
