Opsmatic Puppet Reporter - Puppet Module
======================

This module installs and configures the Opsmatic Puppet Reporter.

Requirements
------------

The Opsmatic Puppet Reporter is supported on the following platforms:

  * Ubuntu: 10.04, 11.04, 11.10, 12.04, 12.10, 13.04 and 13.10.

Usage
-----

To use this module you will need to set the variable `$token` in
your puppet configuration:

    class { 'opsmatic::puppet_reporter':
      token => 'my_integration_token',
    }

or, to purge the puppet\_reporter from your hosts:

    class { 'opsmatic::puppet_reporter':
      ensure => 'absent';
    }

and make sure to set the report setting in your `puppet.conf` to true in order to turn on reporting capabilities on agent nodes:

    [agent]
        report = true

After that, the manifest will handle the appropriate platform detection and configuration. For all supported platforms, the following steps are carried out:

* The Opsmatic Beta repository is configured in your hosts package manager.
* An update is triggered.
* The latest version of the Puppet reporter is installed and started.

The Puppet reporter will run as a daemon waiting for changes performed by Puppet runs, and reporting the results to Opsmatic.

Attributes
----------

* `$token` - this is your integration token.

Support
-------

Please create bug reports and feature requests in [GitHub issues] [1]. And feel free to contribute:

1. Fork it ( https://github.com/opsmatic/puppet-opsmatic/fork ).
2. Create your feature branch (`git checkout -b my-new-feature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin my-new-feature`).
5. Create a new Pull Request.

[1]: https://github.com/opsmatic/puppet-opsmatic/issues

Author:: Opsmatic Inc. (<support@opsmatic.com>)
