# puppet-autossh

Forked from [jfryman/puppet-autossh](https://github.com/jfryman/puppet-autossh) to make the configuration more flexible and some usage examples.

## Example usage

```puppet
autossh::tunnel { "tunnel_name":
  # Common parameters
  remote_host   => "some.ssh.host", # There's no way to specify additional ssh options so we piggyback on this until we fork and patch puppet-autossh
  remote_user   => "some_user",
  user          => "user_to_run_autossh_as",
  ssh_options   => "-L 8000:localhost:80",
  # Other parameters
  monitor_port  => "See monitor port in autossh docs", # If you leave this out, it'll use OpenSSH ServerAlive which is much better,
  # Refer to the autossh docs
  gatetime      => "See AUTOSSH_GATETIME",
  first_poll    => "See AUTOSSH_FIRST_POLL",
  poll          => "See AUTOSSH_POLL",
  maxstart      => "See AUTOSSH_MAX",
  maxlifetime   => "See AUTOSSH_MAXLIFETIME",
  logfile       => "See AUTOSSH_LOGFILE"
}
```
