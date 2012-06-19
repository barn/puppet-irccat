# Report processor that outputs to irccat.

Take http://docs.puppetlabs.com/guides/reporting.html add in
https://github.com/RJ/irccat and you get IRC reports of when things are
broken in Puppet:

<pre>
stringbot: Puppet failed for ptest1.internal.pl https://dashboard01.prod01.pdx.int.puppetlabs.net/nodes/ptest1.internal.pl see http:////github.com/puppetlabs/topsecret-puppet-codes for 83d44e9
</pre>

It tells you the SHA1 if you've configured the SHA1 to be your
config_version, it links to the report in dashboard, if it can find it, or
a search for that host if not.

It ignores hosts that are CTRL-Ced.

It doesn't tell you on weekends!

It ignores things that aren't in production environment. (even if they
break compiling before the environment is set, so long as you use
/etc/puppet/environments as your path to your envs.)

# configuration.

YAML, as it's Ruby, and it's illegal to use anything else. ignore_hosts is
an array of hosts to not message about.

