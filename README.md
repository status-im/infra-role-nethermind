# Description

This role configures a [Nethermind](https://github.com/NethermindEth/nethermind) Ethereum execution layer node.

The Docker image used by default is [nethermind/nethermind](https://hub.docker.com/r/nethermind/nethermind).

# Configuration

The only mandaotry settings is the account password, which can be set to an empty string:

```yaml
nethermind_account_pass: 'my-secret-password'
```

Other important settings are:

```yaml
nethermind_network_name: 'mainnet'
nethermind_service_name: 'nethermind-{{ nethermind_network_name }}'
nethermind_sync_mode: 'snal'
nethermind_log_level_name: 'info'
nethermind_consul_extra_tags: ['mytag']
```
By default we create a [Consul service definition](https://www.consul.io/docs/agent/services.html), disable it using:
```yaml
nethermind_consul_enabled: false
```
For the rest see the [`defaults/main.yml`](/defaults/main.yml) config file.

# Known Issues

* Regular RPC endpoint appears to require JWT auth
