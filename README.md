#Vagrant_Chef
---

This Project is to learn something about
- Vagrant
- Chef (using chef-solo)

Maybe I will add some words for you to follow my learnings. You are welcome to give me input or ask questions.
But remind this is a learning for me I try to share.

This tutorial is spited in different parts (chapters). You can find them in the according branches. 
---

#Chapter 1
Set up the basis

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

##License and Author

Project was created by QuaxelBrod

Licensed under MIT license
