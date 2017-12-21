# ansible_exec_repo
Ansible Repository for testing ansible using test kitchen with Exec Driver.

The exec driver allows ansible to be driven from your workstation, (This provides similar functionality to to the kitchen-ansiblepush driver)

This demonstrates using test-kitchen, ansible to build a server with ansible automatically installed and run from your workstation.

## Workstation Software Installation

The first thing you need to do is install the test-kitchen environment on your workstation.
A useful link is: http://misheska.com/blog/2013/12/26/set-up-a-sane-ruby-cookbook-authoring-environment-for-chef/

The follow instructions are for Windows PC (it will be similar for Mac):

1. Download and install the Windows RubyInstaller for 64 bit Ruby 2.4 from http://rubyinstaller.org/downloads.
   * Check the option to add ruby to your path.
2. Download and install the Windows Ruby DevKit for use with Ruby 2.4 and above (64bits version only) from http://rubyinstaller.org/downloads.
3. Then install the following gems
  * gem install test-kitchen
  * gem install kitchen-ansible
4. git clone the repository https://github.com/neillturner/ansible_exec_repo
```
kitchen list
```
This will return a list if everything is correctly installed.

## Create Servers in Virtual Box on your Workstation.
```
kitchen create ansible-centos-72 -l debug
```

## Build the server.
```
kitchen converge ansible-centos-72 -l debug
```

## Destroy the server.
```
kitchen destroy ansible-centos-72 -l debug
```
##




