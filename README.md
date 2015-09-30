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


 
##License and Author

Project was created by QuaxelBrod

Licensed under MIT license
