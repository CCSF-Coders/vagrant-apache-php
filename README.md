### Overview ###

A Vagrantfile that allows for a quick and easy way to begin working on features for the Coders Club website.
### Pre-setup ###

One problem is that we have many potential developers and only one website. If all of them all worked out of the same directory, we would write over the top of each others code.

Another problem is that we don't want to screw up the website. If even one developer makes a silly change, it could put the website offline.

The solution is Vagrant. Vagrant will:

* Download and install a local virtual machine with Ubuntu as the operating system.
* Install Apache and PHP5 on that virtual machine.
* Forward port 6969 on the VM.
* Download the latest version of the website off of Github.

This allows each developer to develop against a mock server that behaves (almost) the same as the Hills server that the real website runs on. As a developer, you can write code locally, share it with the VM, and open up your browser to view your changes instantly and safely! When your all done and your code is 100% working, push to the repo with confidence that your code will work when it goes live.

### How do I get set up? ###

* Download & install Vagrant: [http://www.vagrantup.com/downloads.html](http://www.vagrantup.com/downloads.html)
* Download & install VirtualBox: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
* Clone this repo to your computer.

Then run the following command in your folder where you cloned this repo (where the Vagrantfile is):

NOTE: This will take ~10 minutes to run fully.
```
vagrant up
```

Thats it!

### Where do I code? ###
Open up the public_html folder and code away. The files in the public_html folder should have the latest code changes to the website. Any changes you make to the files inside the public_html folder are sym-linked to apache's /var/www (in other words: any changes you make will be viewable in your browser)

### How do I view the website ###
Open up your browser and navigate to

```
localhost:6969
```

You should see the index.php page. Treat the localhost:6969 like you would the url "hills.ccsf.edu/coders".

### Who do I talk to? ###

Repo owner: Tyler Brothers <tylerbrothers1@gmail.com>

[For the CCSF Coders Club](ccsf.edu/coders)
