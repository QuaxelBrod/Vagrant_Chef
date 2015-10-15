#Vagrant_Chef

This Project is to learn something about
- Vagrant
- Chef (using chef-solo)

Maybe I will add some words for you to follow my learnings. You are welcome to give me input or ask questions.
But remind this is a learning for me I try to share.

This tutorial is spited in different parts (chapters). You can find them in the according branches.
 
---

#Chapter 4

Fine. I whant to make som custom configurations on the nginx. Then start a node server with a simple application. After 
that, there is the need to put the things on different machines and start both with my vagrant file.

There is a lot to do with chef (cookbooks, roles and environments) but also with vagrant.

#### Add a node application server

As before I start with a cookbook from https://supermarket.chef.io/cookbooks/nodejs
Add `cookbook 'nodejs', '~> 2.4.2'` to Berksfile and
`chef.add_recipe "nodejs::nodejs_from_package"` to Vagrantfile.
This installs the deafult package for node inclusive npm. fine. start it with a simple express app. Find it in 
`nodeapplication`
Now I can start the box, ssh in and use `cd /vagrant/nodeapplication` `npm install` `node expressapp.js` to start a 
node server in my box...
Lets chef do this things:
Add new cookbook: `knife cookbook create startnodeserver -o site-cookbooks`
Add this to Berksfile and add in Vagrantfiles run ist (remove old nodejs recipe).
I moved the recipes run list to the new cookbook, because if I install the application this are my dependencies. Things 
should stay together.



 
##License and Author

Project was created by QuaxelBrod

Licensed under MIT license
