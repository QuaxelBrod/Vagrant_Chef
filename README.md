#Vagrant_Chef

This Project is to learn something about
- Vagrant
- Chef (using chef-solo)

Maybe I will add some words for you to follow my learnings. You are welcome to give me input or ask questions.
But remind this is a learning for me I try to share.

This tutorial is spited in different parts (chapters). You can find them in the according branches.
 
---

#Chapter 2


Adding some more features

##do some additional usefull magic
There are many cookbooks around. Hopefully we do not need to download them and maintain them on our own. Think the chef 
server which is simulated by chef solo should do all this stuff. But therefore we need some additional stuff.
Lets start

###Add some tools (tools is all we need ;) )
####Ruby
If you do not have already Ruby installed, install it now. Go to https://www.ruby-lang.org and find the version for 
your platform. I used Ruby 2.2. For windows you find the installer here: http://rubyinstaller.org/downloads/
    
#####Windows only
For linux you should consult the online documentation from https://www.ruby-lang.org

Next tool is the Ruby Development Kit. This tool enables native code compilation for ruby gems. Think about a library 
wants to use native windows APIs. Therefore the lib contains native platform code which must be compiled on destination 
platform. This package is an easy going for windows. It registers a compilation platform without the need to struggle 
with Visual Studio. 
So got to http://rubyinstaller.org/downloads/ and download the DevKit for your Ruby and platform.
Hint: If you get compile errors check if you have installed 32 or 64 Bit versions... DevKit should match the ruby 
installation. Test the installation with `gem install json --platform=ruby`

#####Chefdk
That is the chef development kit. 

####knife solo
knife is the right tool to configure (not at all) chef cookbooks. For chef configurations you need knife to struggle 
with the chef server, add roles and cookbooks and so on. All necessary thins for your infrastructure or achitecture are 
stored on the chef server. Remember, that I right now want a self contained project wothout a chef server. But have in 
mind to move to a chef server. That is why I used chef solo. And so I need knife solo to struggle around with my 
chef solo environment.
Now run `gem install knife-solo` to get knife solo installed

####berkshelf
This is something like a Cookbook repository. If you refer to an other cookbook, berkshelf can resolve this for you, 
resolve all necessary dependencies and stor it in a local repository.
There is a vagrant-berkshelf plugin. To install and enable it just type:
`vagrant plugin install vagrant-berkshelf`
Then add a config line to the vagrant config file:
`config.berkshelf.enabled = true`
! Berkshelf needs chefdk 

Do not install berkshelf via roby gems. That is not recommended.

###Do some thing
now lets try to setup a new cookbook hirarchy:
`knife solo init knife_solo`
This creates a new directory chef_solo. 






##License and Author

Project was created by QuaxelBrod

Licensed under MIT license
