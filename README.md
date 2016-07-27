# BOSH Half Day Workshop

This is a half day training on BOSH that will allow ops teams to get familiar with BOSH concepts and also start using BOSH in their environments.

### Prerequisites

* [VirtualBox](https://www.virtualbox.org/): 5.0+
* [Vagrant](http://www.vagrantup.com/)
* 6GB of available memory for BOSH lite VM.  See optional section below to tweak this setting.
* ...or AWS account.
* Internet connection (or [Dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html) or [Acrylic](http://mayakron.altervista.org/wikibase/show.php?id=AcrylicHome)) required for wildcard DNS resolution

### VirtualBox setup

1. Clone the BOSH lite repo from Github - `git clone https://github.com/cloudfoundry/bosh-lite.git`
2. cd to bosh-lite (repo) directory and run `vagrant up`.
3. Run `vagrant ssh` to login to the VM as the *vagrant* user.
4. Run `git clone https://github.com/tgreenyc/cf-bosh-workshop.git` into *vagrant* home directory.  NOTE: This should be run _inside_ VirtualBox VM.
5. Run `cd cf-bosh-workshop` and you are prepared to start the [Labs](Labs)

### (optional) Changing memory usage for BOSH lite

This optional step should be performed if you don't have enough memory on your local machine.  It is strongly recommended that you don't go below 4GB for performance reasons.
Open the Vagrantfile inside of the bosh-lite repo directory that you clone, and create a new line below: 

```ruby
config.vm.provider :virtualbox do |v, override|

```

And add:

```ruby
  v.memory = 4096
```

# Copyright

See [LICENSE](LICENSE) for details.
Copyright (c) 2016 [Pivotal Software, Inc](http://www.pivotal.io/).
