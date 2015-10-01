#Vagrant_Chef

This Project is to learn something about
- Vagrant
- Chef (using chef-solo)

Maybe I will add some words for you to follow my learnings. You are welcome to give me input or ask questions.
But remind this is a learning for me I try to share.

This tutorial is spited in different parts (chapters). You can find them in the according branches.
 
---

#Chapter 3

I have learned how to set up a vagrant, chef_solo and berkshelf setup. Fine. What is missing now is to do all the magic 
with this suer cute cookbooks from chef.io

### Running apt-update
First thing we often neet is to update the packetmanager cache and install some packages. Many cookbooks relay on the 
apt cookbook. So lets fire apt to find out how it works...
Go to: https://supermarket.chef.io/ and search for `apt` and find this one: https://supermarket.chef.io/cookbooks/apt
Now you find the code to include this cookbook in Berkshelf:
`cookbook 'apt', '~> 2.8.2'`
Just add this line in front of your hello World cookbook in Berksfile
And fire `vagrant provision`
And now add some apt things:
If you just add the cookbook to Vagrant file chef run list he default recipe s started.
`chef.add_recipe "apt"`

### Installing nginx (1)
I decided to install nginx to the machine. Here I want to learn how to install packets and do some configuration stuff.
So start to setup a coockbook as learned with `knife cookbook create -o chef_solo/site-cookbooks LearnNginx`
I do it this way, because knife creates all the necessary files. You can also create the files by hand.
Remember to add this to Berksfile. 
In the default recipe add the line `package nginx` this should do the magic on the VM. Remember to add the recipe to the 
runlist in the vagrant file.
Thats it. now I have a running nginx on my box. But now lets have the output in our webbrowser:
Two ways

#### Portforwarding
Configure vagrant to forward a Port from the VM to your local box. That is just like having a ssh with -l:
Just add a lint to your vagrant file: `config.vm.network "forwarded_port", guest: 80, host: 8081`
I have used port 8081 because 8080 sometimes make troubles in windows. You may need a `vagrant halt` and `vagrant up` 
again.
Now open a browser and go to http://127.0.0.1:8081 

#### Private Network
Vagrant file gives good suggestions, how to use netork configurations. test the other ones


 
##License and Author

Project was created by QuaxelBrod

Licensed under MIT license
