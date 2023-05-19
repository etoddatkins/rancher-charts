# Private Docker Registry

## Installation Example

```bash
helm upgrade --install docker-registry -f values.yaml .
```

Add "127.0.0.1 private-registry.local" to /etc/hosts

## Testing

```bash
curl -X GET private-registry.local/v2/_catalog
```

## Values

[see values.yaml](./values.yaml)

