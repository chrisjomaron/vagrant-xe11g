vagrant-xe11g
=============

Motivation:

There are times you need an Oracle database, but you don't want to go into all of the effort and cruft of creating one.

This creates an Oracle XE 11g database which is fully functional to use with the HR schema unlocked in about 5 minutes.

It is very lean and mean.  It boots, via the Vagrantfile, with 512mb RAM allocated to the VM and has the bare minimum of files on the Vagrant box.
It also has 1GB of swap.

Kit Needed:

Oracle 11g XE R2

http://www.oracle.com/technetwork/products/express-edition/overview/index.html

These scripts use:

- oracle-xe-11.2.0-1.0.x86_64.rpm


I added some niceties for this box.

- vagrant user is a member of the dba group.
- I have added the oracle_env.sh script to the .bashrc for vagrant so you can use sqlplus in the command line
- Password are "oracle" for system and sys.  You can see those in the response file in the root of the project.
- Password for root is vagrant (like..like all vagrant boxes) database.
- Related to (2) above, I have a really basic shell script that can be used to incorporate your own schemas when you do the vagrant up or run seperately.  It is a nice example that I found and hacked.
- You can access the database in either of the following ways from your host machine:

  - http://localhost:8080/apex/f?p=4950:2:2370103243114289::NO:::
  - Via the normal tns listener port of 1521 from your host machine...for tools like JDeveloper or Eclipse.

The one area which I needed a little thought on is handling the swap file if you perform a halt.  I don't add the on the fly created swap file to fstab.  If someone wants to help with that...I will welcome that.  Therefore, I would use a vagrant suspend command. Once running...why do you need to reboot now?  Just do a pause.

I will be posting some more information on http://vbatik.wordpress.com so stay tuned. 

Enjoy...

/Matt

Twitter: @baldwinonline



