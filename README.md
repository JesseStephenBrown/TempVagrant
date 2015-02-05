
Instructions
------------
1. Download and install [Vagrant](https://www.vagrantup.com/)
2. In this repository, run `vagrant up`. This will collect
the ubuntu trusty tahr 64-bit image, and then will use the
bootloader script to install numpy, matplotlib, nltk, and lda
(and any dependencies). This should only happen the first time you
use `vagrant up` or any time you attempt to re-provision.
3. Log in to the vagrant box with `vagrant ssh`
4. Test by opening an interactive python shell and test the imports with the following:

  ```
  vagrant@vagrant-ubuntu-trusty-64:~$ python
  Python 2.7.6 (default, Mar 22 2014, 22:59:56)
  [GCC 4.8.2] on linux2
  Type "help", "copyright", "credits" or "license" for more information.
  >>> import numpy
  >>> import nltk
  >>> import matplotlib
  >>> import lda
  >>> exit()
  ```

5. Log out of the vagrant shell with `logout` and gracefully shut down the machine with `vagrant halt` once
you return to your machine's prompt.

How this works
--------------
Vagrant runs a virtual machine which shares the directory it is run from (the
directory with the Vagrantfile). Typically, the Vagrantfile is placed in the root
of whatever repository you are using, so it can access all the files in the repo.
The use of Vagrant allows us to ensure we are using the same environment to test
and run our code, so there is no confusion about which environment settings work
and don't work with the application, and no one can claim, "...but it worked on my
machine!".

Also, installing libraries can be a pain and this automates that.

Issues
------
Report any issues through the issues link for this repository.
