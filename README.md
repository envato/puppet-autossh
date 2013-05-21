# puppet-autossh

Forked from [jfryman/puppet-autossh](https://github.com/jfryman/puppet-autossh) to make the configuration more flexible and some usage examples.

## Example usage

```puppet
autossh::tunnel { 'tunnel_name':
  remote_host   => "some.ssh.host", # There's no way to specify additional ssh options so we piggyback on this until we fork and patch puppet-autossh
  remote_user   => 'some_user',
  user          => 'user_to_run_autossh_as,
  ssh_options   => '-L 8000:localhost:80'
}
```
