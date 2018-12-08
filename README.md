# Nginx cookbook

## Requirements
Create an nginx cookbook that provision a virtual machine

### Unit tests :

  - Apt update running correctly
  - Nginx will install
  - The reverse proxy template will be created
  - A link will be created between the proxy.conf file in sites-available and sites-enabled
  - A link will be removed between the default file in sites-available and sites-enabled


### Integration tests :

  - Nginx is installed
  - Nginx is running and is enabled
  - Nginx is listening to port 80
  - A request to localhost:80 will return 502 if reverse proxy is working correctly


## How to use
- In your Berksfile, add this line:
```ruby
cookbook "nginx", git: "git@github.com:Els-Sparta/NginxCookbook.git"
```
- Run this line in your console:
```bash
berks vendor cookbooks
```
- This cookbook is now provisioned !

If you're using vagrant, add in your Vagrantfile:
```ruby
config.vm.provision("chef_solo") do |chef|
    chef.add_recipe("nginx::default")
  end
```
