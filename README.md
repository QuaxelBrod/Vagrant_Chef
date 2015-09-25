#Vagrant_Chef
---

This Project is to learn something about
- Vagrant
- Chef (using chef-solo)

Maybe I will add some words for you to follow my learnings. You are welcome to give me input or ask questions.
But remind this is a learning for me I try to share.

---

##Prerequires
---

- First you need a hypervisor. I use VirtualBox https://www.virtualbox.org/ 
- Then you need Vagrant. Find it here: https://www.vagrantup.com/ Just install it anywhere. Under Windows check the default path. You may want to change it. 

---

##Set up vagrant
Just open a comandline in the directory an type in 
`vagrant init`
That creates your initial Vagrantfile. Here you configure all your things...

Next I added some parts for the VM configuration. Initially only the available memory.

Then add the chef_zero provisioner. I decided to put all chef files in a separate folder called chef.
Just add a folder cookbooks in chef and put all your cookbooks there. I started with a simple HelloWorld example.

## do some additional usefull magic
There are many cookbooks around. Hopefully we do not need to download them and maintain them on out own. Think the chef server
witch is simulated by chef solo should do all this stuff.
Lets start
### Add some tools (tools is all we need ;) )
On the command line install bundler:
`gem install bundler`
With bundler you can setup project specific gems. gems are like librarys for ruby. So one can enssure that if someone 
checkout the project all you need is to run bundle install and all ruby libraries are up with the right version.


##License and Author

Project was created by QuaxelBrod

Licensed under MIT license
